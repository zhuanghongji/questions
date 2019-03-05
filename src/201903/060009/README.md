
# 描述一下 Volley 的磁盘缓存

## 自答

### Volley 的磁盘缓存

Volley 会将每次通过网络请求到的数据，采用 FileOutputStream，写入到本地的文件中。这个缓存文件，是声明在一个SD卡文件夹中的(也可以是getCacheFile())。如果不停的请求网络数据，这个缓存文件夹将无限制的增大，最终达到SD卡容量时，会发生无法写入的异常(因为存储空间满了)。

DiskBasedCache#pruneIfNeeded()

```java
private void pruneIfNeeded(int neededSpace) {
    if ((mTotalSize + neededSpace)  mMaxCacheSizeInBytes) {
        return;
    }

    long before = mTotalSize;
    int prunedFiles = 0;
    long startTime = SystemClock.elapsedRealtime();

    IteratorMap.EntryString, CacheHeader>> iterator = mEntries.entrySet().iterator();
    while (iterator.hasNext()) {
        Map.EntryString, CacheHeader> entry = iterator.next();
        CacheHeader e = entry.getValue();
        boolean deleted = getFileForKey(e.key).delete();
        if (deleted) {
            mTotalSize -= e.size;
        } else {
            // print log
        }

        iterator.remove();
        prunedFiles++;
        if ((mTotalSize + neededSpace)  mMaxCacheSizeInBytes * HYSTERESIS_FACTOR) {
            break;
        }
    }
}
```

其中 `mMaxCacheSizeInBytes` 是构造方法传入的一个缓存文件夹的大小，如果不传默认是5M的大小。

通过这个方法可以发现，每当被调用时会传入一个 `neededSpace`，也就是需要申请的磁盘大小(即要新缓存的那个文件所需大小)。首先会判断如果这个 `neededSpace` 申请成功以后是否会超过最大可用容量，如果会超过，则通过遍历本地已经保存的缓存文件的 header (header 中包含了缓存文件的缓存有效期、占用大小等信息)去删除文件，直到可用容量不大于声明的缓存文件夹的大小。

其中 `HYSTERESIS_FACTOR` 是一个值为 `0.9` 的常量，应该是为了防止误差的存在吧。


### Volley 缓存命中率的优化

在缓存内容可能超过缓存文件夹的大小时，删除的逻辑是直接遍历 header 删除。这个时候删除的文件有可能是我们上一次请求时刚刚保存下来的，屁股都还没坐稳呢，现在立即删掉，有点舍不得啊。

如果遍历的时候，判断一下，首先删除超过缓存有效期的(过期缓存)，其次按照LRU算法，删除最久未使用的，岂不是更合适？


### Volley 缓存文件名的计算

```java
private String getFilenameForKey(String key) {
    int firstHalfLength = key.length() / 2;
    String localFilename = String.valueOf(key.substring(0,firstHalfLength).hashCode());
    localFilename += String.valueOf(key.substring(firstHalfLength).hashCode());
    return localFilename;
}
```

为什么会要把一个 key 分成两部分，分别求 hashCode，最后又做拼接？

目的是为了尽可能避免 hashcode 重复造成的文件名重复(求两次 hash 两次都与另一个 url 重复的概率总要比一次重复的概率小吧)。

顺带再提一点，就像上面说的，概率小并不代表不存在。但是 Java 计算 hashcode 的速度是很快的，应该是在效率和安全性上取舍的结果吧。