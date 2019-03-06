# Activity 状态的保存与恢复

## 自答

![](./res/001.png)

由上图可知，系统在内存不足时会杀死不可见的 Activity，如果我们需要保存一些临时状态并在 Activity 重建后恢复，则可以在 `onSaveInstanceState()` 方法中保存 Activity 的状态，然后在 `onCreate()` 或 `onRestoreInstanceState()` 方法中进行恢复。

示例代码如下：

```java
public class SaveStateActivity extends Activity {
  
  public static final String TAG = "SaveStateActivity";
 
  @Override
  public void onCreate(Bundle savedInstanceState) {
    if (savedInstanceState!=null) {
      Log.v(TAG, savedInstanceState.getString("data"));
    }
    super.onCreate(savedInstanceState);
    setContentView(R.layout.main);
    Log.v(TAG, "onCreate");
  }
    
	@Override
	protected void onRestoreInstanceState(Bundle savedInstanceState) {
		Log.v(TAG, savedInstanceState.getString("data"));
		super.onRestoreInstanceState(savedInstanceState);
		Log.v(TAG, "onRestoreInstanceState");
	}
	
	@Override
	protected void onSaveInstanceState(Bundle outState) {
		outState.putString("data", "example");
		super.onSaveInstanceState(outState);
		Log.v(TAG, "onSaveInstanceState");
	}
}
```

场景 1：运行应用后点击 Home 键，然后再重新进入应用
* 点击 Home 键时，`onSaveInstanceState()` 方法会在 `onPause()` 方法前执行。
* 程序恢复执行时，会调用 `onRestart()` 方法，但没有调用 `onRestoreInstanceState` 方法。 

场景 2：运行应用后点击 Back 键
* 系统不会调用 `onSaveInstanceState()` 方法，因为点击 Back 键表明用户已经明确想要退出这个页面，无需进行保存任何状态。
* 也就是说 `onSaveInstanceState()` 方法的调用是不确定的，如果想要持久化数据的话需要在 `onPause()` 或其它方法中执行。

场景 3：运行应用然后在 EditText 中输入字符串，然后切换横竖屏
* 发现 EditText 中的字符串还在，说明 UI 是会自动保存和恢复的。
* `onRestoreInstanceState()` 方法在 `onStart()` 之后执行，但会在 `onResume()` 之前。