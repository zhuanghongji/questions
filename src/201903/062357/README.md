# 为什么 AsyncTask 只能执行一次

## 自答

准确的说应该是：**一个 AsyncTask 对象只能执行一次，即只能 `execute` 一次。**

我们先来验证一下：

```java
public class MyAsyncTask extends AsyncTask<Void, Void, Void> {

    private String mName;

    MyAsyncTask(String name) {
        mName = name;
    }

    @Override
    protected Void doInBackground(Void... voids) {
        try {
            Thread.sleep(3000);
            Log.i("MyAsyncTask", "doInBackground, name = " + mName);
        } catch (Exception e) {
            e.printStackTrace();
        }
        return null;
    }
}
```

如果同时执行一个 AsyncTask 对象会怎样？

```java
MyAsyncTask task = new MyAsyncTask("abc");
task.execute();
task.execute();

/* 
有一条输出日志：
I/MyAsyncTask: doInBackground, name = abc

但会导致应用闪退，提示：java.lang.IllegalStateException: Cannot execute task: the task is already running.
/*
```


如果先让一个 AsyncTask 对象执行完，然后在次执行该对象会怎样？

```java
final MyAsyncTask task = new MyAsyncTask("ABC");
task.execute();

Handler handler = new Handler();
handler.postDelayed(new Runnable() {
    @Override
    public void run() {
        task.execute();
    }
}, 5000);

/* 
有一条输出日志：
I/MyAsyncTask: doInBackground, name = ABC

也会导致闪退，提示：java.lang.IllegalStateException: Cannot execute task: the task has already been executed (a task can be executed only once)
/*
```

如果多个 AsyncTask 对象同时执行会怎样？

```java
new MyAsyncTask("1").execute();
new MyAsyncTask("2").execute();
new MyAsyncTask("3").execute();
new MyAsyncTask("4").execute();
new MyAsyncTask("5").execute();

/*
有多条日志输出，但不闪退：
I/MyAsyncTask: doInBackground, name = 1
I/MyAsyncTask: doInBackground, name = 2
I/MyAsyncTask: doInBackground, name = 3
I/MyAsyncTask: doInBackground, name = 4
I/MyAsyncTask: doInBackground, name = 5
*/
```


**为什么会闪退？**

看下 AsyncTask 执行时的源码就知道了：

```java
@MainThread
public final AsyncTask<Params, Progress, Result> execute(Params... params) {
    return executeOnExecutor(sDefaultExecutor, params);
}

@MainThread
public final AsyncTask<Params, Progress, Result> executeOnExecutor(Executor exec,
        Params... params) {
    if (mStatus != Status.PENDING) {
        switch (mStatus) {
            case RUNNING:
                throw new IllegalStateException("Cannot execute task:"
                        + " the task is already running.");
            case FINISHED:
                throw new IllegalStateException("Cannot execute task:"
                        + " the task has already been executed "
                        + "(a task can be executed only once)");
        }
    }

    mStatus = Status.RUNNING;
    onPreExecute();
    mWorker.mParams = params;
    exec.execute(mFuture);
    return this;
}
```

**为什么这样设计？**

考虑到线程安全问题。

## 其它

推荐阅读：
* [AsyncTask 只能执行一次](https://blog.csdn.net/zhaoyangfang/article/details/76100607)