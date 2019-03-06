# 谈谈 Activity 的生命周期

## 自答

![](./res/activity_lifecycle.png)

Activity 启动：
* `onCreate()` -> `onStart()` -> `onResume()`，Activity 进入运行状态。

Activity 进入后台：
* 切换到新的 Activity 或按 Home 键回到手机主屏时，当前 Activity 生命周期变化，`onPause()` -> `onStop()`，进入停滞状态。

Activity 返回前台：
* `onRestart()` -> `onStart()` -> `onResume()`，再次回到运行状态。

Activity 进入后台且当前系统内存不足：
* 系统会 kill 掉这个后台状态的 Activity，再次回到这个 Activity 时，则会 `onCreate()` -> `onStart()` -> `onResume()`。

锁定屏幕或解锁屏幕：
* 锁定时会调用 `onPause()`，但不会调用 `onStop()`。开屏后则则调用 `onResume()`。

横竖屏切换时 Activity 的生命周期：
* TBD

弹出 Dialog 的时候按 Home 键时 Activity 的生命周期：
* TBD

两个 Activity 之间跳转时的生命周期：
* TBD

下拉状态栏时 Activity 的生命周期：
* TBD

