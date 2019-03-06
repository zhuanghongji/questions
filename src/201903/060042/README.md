# Activity 的四种启动模式和使用场景

## 自答

### 标准模式 (standard)

默认的启动模式，每次启动一个 Activity 时都会在栈中新建一个实例。

在这种模式下，可以有多个相同的实例，也允许多个相同的 Activity 叠加。一般情况下如果我们对页面数据的实时性有要求的话，都会使用标准启动模式。

在这种启动模式下，每次都会新建 Activity 对象，不仅耗时而且还会造成内存的浪费。


### 栈顶复用模式 (singleTop)

在这种启动模式下，如果栈中已经有一个实例且正处于栈顶，则会直接复用该实例。如果不是这样的话，就会创建一个新的实例。

与 Standard 相比，栈顶复用可以有效减少 Activity 重复创建时对资源的消耗，但在实际开发中要根据具体情况而定，不能一概而论。

栈顶复用模式适用于接收通知启动的内容显示页面。例如，某个视频 App 在联网之后一口气收到了 N 多个通知，点开其中一个后会开始播放视频，看完了后点开第二个通知时会直接在原来的界面上刷新视频，不会出现再次打开的动作，用户体验也好。


### 栈内单例模式 (singleTask)

在这种启动模式下，如果发现栈中有对应的 Activity 实例，则会将在这个 Activity 实例之上的其它 Activity 全部出栈，使得该 Activity 成为栈顶对象而显示在最前面。

在项目中我们都会有一个主页面 (一般命名为 MainActivity 或 HomeActivity)，因为主页面的启动和显示在栈顶的次数都比较多，所以我们通常都会讲主页面的启动模式设置为 singleTask 模式。


### 堆内单例 (singleInstance)

指定了 singleInstance 启动模式的 Activity，在整个 Android 系统中只会有一个实例。

通常我们会将暴露给其它应用调用的入口页面设置为 singleInstance 启动模式。比如说，微信的分享页面、手机拨号页面等。


## 其它

推荐阅读：
* [Activity 四种启动模式常用场景](https://blog.csdn.net/weixin_41101173/article/details/79691159)
* [Activity 四种启动模式及 onNewIntent() 方法、taskAffinity 属性分析](https://blog.csdn.net/weixin_41101173/article/details/79689601)