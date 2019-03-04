# questions

自问自答

* [ ] 待初答
* [ ] [待完善](#questions)
* [x] [已完成](#questions) 

> 注：认真对待每一个答案。


## Java

[⇧ 返回顶部](#questions)

* [ ] 什么是面向对象（OOP）
* [ ] String、StringBuilder 和 StringBuffer 有什么区别
* [ ] == 和 equals 和 hashCode 有什么区别
* [ ] 说说你对 final 修饰符的理解
* [ ] 说说你对泛型的理解
* [ ] 泛型中 extends 和 super 的区别
* [ ] 描述下 Java 中的异常处理机制
* [ ] 什么是 HashMap，描述下其实现原理
* [ ] HashMap、Hashtable 和 HashSet 这三者有什么联系和区别
* [ ] 列举下 Java 的集合和继承关系
* [ ] 说下你对抽象类和接口的理解，以及两者的相同点和不同点
* [ ] 父类的静态方法能否被子类重写
* [ ] 描述下类的加载机制
* [ ] 说说你对 Java 反射的理解
* [ ] 什么是动态代理
* [ ] 在 Java 中 wait、yield 和 seelp 方法的不同
* [ ] 描述下 Java 中的内存分配
* [ ] [什么是堆污染](./src/201812/020937/)

[]()

* [ ] 什么是多态，实现多态的机制是什么
* [ ] 接口（Interface）与抽象类（Abstract Class）的区别
* [ ] 重写（Override）与重载（Overload）的区别
* [ ] 父类的静态方法能否被子类重写
* [ ] 静态属性和静态方法是否可以被继承，是否可以被重写，为什么
* [ ] 什么是内部类，内部类、静态内部类、局部内部类和匿名内部类的区别及作用
* [ ] == 和 equals() 和 hashCode() 的区别
* [ ] Integer 和 int 之间的区别
* [ ] String 转换成 Integer 的方式及原理
* [ ] 自动装箱实现原理，类型转换实现原理
* [ ] String 为什么要设计成不可变的
* [ ] final、finally 和 finalize 的区别
* [ ] static 关键字有什么作用
* [ ] 列举 Java 的集合以及集合之间的继承关系
* [ ] List、Set、Map 的区别
* [ ] ArrayList、LinkedList 的区别
* [ ] HashMap，HashTable，ConcurrentHashMap 实现原理以及区别
* [ ] HashSet 与 HashMap 怎么判断集合元素重复
* [ ] String、StringBuffer、StringBuilder 之间的区别
* [ ] 什么是序列化，怎么实现，有哪些方式
* [ ] 泛型中 extends 和 super 的区别
* [ ] 对 Java 的异常体系的了解
* [ ] 对解析与分派的了解
* [ ] 静态代理和动态代理的区别，有什么场景使用
* [ ] 谈谈对 Java 状态机理解

[]()

* [ ] 线程和进程的区别
* [ ] 开启线程的三种方式
* [ ] 如何正确的结束一个Thread
* [ ] Thread 与 Runnable 的区别
* [ ] run() 与 start() 方法的区别
* [ ] sleep() 与 wait() 方法的区别
* [ ] wait 与 notify 关键字的区别
* [ ] synchronized 关键字的用法、作用及实现原理
* [ ] volatile 关键字的用法、作用及实现原理
* [ ] transient 关键字的用法、作用及实现原理
* [ ] ReentrantLock、synchronized、volatile 之间的区别
* [ ] 什么是线程池，如何使用
* [ ] 多线程断点续传的实现原理
* [ ] 什么是深拷贝和浅拷贝
* [ ] Java 中对象的生命周期
* [ ] 对并发编程的了解

[]()

* [ ] 简述 JVM 内存模型和内存区域
* [ ] 简述垃圾回收器的工作原理
* [ ] 如何判断对象的生死，垃圾回收算法，新生代，老生代
* [ ] 哪些情况下的对象会被垃圾回收机制处理掉
* [ ] 垃圾回收机制与调用 System.gc() 的区别
* [ ] 强引用、软引用、弱引用、虚引用之间的区别
* [ ] 强引用设置为 null，会不会被回收
* [ ] 简述 ClassLoader 类加载机制
* [ ] 对双亲委派模型的了解
* [ ] String a = "a"+"b"+"c" 在内存中创建几个对象
* [ ] 对 Dalvik、ART 虚拟机的了解
* [ ] 对动态加载（OSGI）的了解
* [ ] 常见编码方式有哪些
* [ ] utf-8 编码中的中文占几个字节，int 型占几个字节

[]()

* [ ] 对 RxJava 的理解，功能与原理，优缺点？


## Kotlin

[⇧ 返回顶部](#questions)

* [ ] 跟 Java 相比，Kotlin 有什么优势
* [ ] Kotlin 是什么，谈谈你对 Kotlin 的理解
* [ ] 当你在项目中同时使用 Java 和 Kotlin，你是如何保证空指针问题的


## Android

[⇧ 返回顶部](#questions)

* [ ] 四大组件是什么
* [ ] Activity 的生命周期
* [ ] Activity 之间的通信方式
* [ ] Activity 各种情况下的生命周期
* [ ] 横竖屏切换时 Activity 的生命周期
* [ ] 前台切换到后台，然后再回到前台时 Activity 的生命周期
* [ ] 弹出 Dialog 的时候按 Home 键时 Activity 的生命周期
* [ ] 两个 Activity 之间跳转时的生命周期
* [ ] 下拉状态栏时 Activity 的生命周期
* [ ] Activity 与 Fragment 之间生命周期比较
* [ ] Activity 的四种 LaunchMode（启动模式）的区别
* [ ] Activity 状态保存与恢复
* [ ] Fragment 各种情况下的生命周期
* [ ] Activity 和 Fragment 之间怎么通信， Fragment 和 Fragment 怎么通信
* [ ] Service 的生命周期和启动方式
* [ ] Service 与 IntentService 的区别
* [ ] Service 和 Activity 之间的通信方式
* [ ] 对 ContentProvider 的理解
* [ ] ContentProvider、ContentResolver、ContentObserver 之间的关系
* [ ] 对 BroadcastReceiver 的了解
* [ ] 广播的分类，使用方式和场景
* [ ] 动态广播和静态广播有什么区别
* [ ] AlertDialog、popupWindow、Activity 之间的区别
* [ ] Application 和 Activity 的 Context 之间的区别
* [ ] Android 属性动画特性
* [ ] 请列举 Android 中常见的布局（Layout）类型，并简述其用法，以及排版效率
* [ ] LinearLayout、RelativeLayout、FrameLayout 的特性对比及使用场景
* [ ] 对 SurfaceView 的了解
* [ ] Serializable 和 Parcelable 的区别
* [ ] Android 中数据存储方式有哪些
* [ ] 屏幕适配的处理技巧都有哪些
* [ ] Android 各个版本 API 的区别
* [ ] 动态权限适配方案，权限组的概念
* [ ] 为什么不能在子线程更新 UI
* [ ] ListView 图片加载错乱的原理和解决方案
* [ ] 对 RecycleView 的了解
* [ ] Recycleview 和 ListView 的区别
* [ ] RecycleView 实现原理
* [ ] Android Manifest 的作用与理解
* [ ] 多线程在 Android 中的使用
* [ ] 区别 Animation 和 Animator 的用法，概述实现原理

[]()

* [ ] 描述下 Activity 的生命周期
* [ ] 介绍不同场景下 Activity 生命周期的变化过程
* [ ] 谈谈你对 Android 中 Context 的理解
* [ ] AsyncTask 的使用方式和版本演进
* [ ] Handler 的工作原理，为什么在子线程中执行 new Handler() 会抛出异常
* [ ] RemoteViews 的作用和工作原理
* [ ] RecyclerView 和 ConstraintLayout 的介绍和使用方式
* [ ] ThreadLocal 的作用和实现原理
* [ ] 描述下 Android 的动态权限：是怎样分类，哪些权限必须要动态申请，请写出权限申请的关键代码
* [ ] 如何理解设计模式的几大原则，你平时在工作中都用过哪几种模式，可以举一个工作中的例子吗，它解决了你的什么问题
* [ ] 给定一个 1000px * [ ] 20000px 的大图，如何正常加载显示且不发生 OOM
* [ ] AndroidStudio 点击 build 之后直到将 Apk 安装到手机上，请详细描述下这个过程的背后到底发生了什么
* [ ] 画出 MVC、MVP 和 MVVM 这三种模式的设计图，并给出它们的适用场景和优缺点
* [ ] 网络的五层划分是什么，TCP 和 UDP 的区别是什么，简述 TCP 的三次握手过程
* [ ] Android 中的线程池有哪些，它们有什么区别，为什么要使用线程池

[]()

* [ ] 画出 Android 的大体架构图
* [ ] 低版本 SDK 如何使用高版本 API
* [ ] AsyncTask 如何使用
* [ ] AsyncTask 机制、原理及不足
* [ ] 如果在 onStop() 的时候做了网络请求，onResume() 的时候怎么恢复
* [ ] Handler 机制和底层实现
* [ ] Handler、Thread、HandlerThread 区别
* [ ] Thread、Looper、MessageQueue、Handler、Message，每个类的功能是什么，这些类之间是什么关系
* [ ] ThreadLocal 原理、实现及如何保证 Local 属性
* [ ] 自定义 View 的流程，如何机型适配
* [ ] 自定义 View 的时怎么获取 View 的大小
* [ ] View 的绘制流程
* [ ] View 的事件传递分发机制
* [ ] requestLayout()，onLayout()，onDraw()，drawChild() 区别与联系
* [ ] invalidate() 和 postInvalidate() 的区别
* [ ] 如何计算一个 View 的嵌套层级
* [ ] Android 动画框架及实现原理
* [ ] 进程和 Application 的生命周期的关系
* [ ] SpareArray 的实现原理
* [ ] SharedPreferences 的实现眼里，是否进程同步，如何做到同步
* [ ] ContentProvider 是如何实现数据共享的
* [ ] ContentProvider 的权限管理
* [ ] Android 系统为什么会设计 ContentProvider
* [ ] Android 线程有没有上限
* [ ] 怎么去除重复代码
* [ ] Android 中开启摄像头的主要流程
* [ ] 对 Bitmap 对象的了解
* [ ] 服务器只提供数据接收接口，在多线程或多进程条件下，如何保证数据的有序到达？
* [ ] SQLite 数据库升级，数据迁移问题
* [ ] 数据库框架对比和源码分析
* [ ] CAS介绍，OAuth 授权机制
* [ ] 谈谈你对安卓签名的理解
* [ ] App 是如何沙箱化，为什么要这么做
* [ ]  如果在 Adapter 中使用应该如何解耦？

[]()

* [ ] 请介绍一下 NDK
* [ ] 如何加载 ndk 库，如何在 jni 中注册 native 函数，有几种注册方式
* [ ] Android 进程分类
* [ ] 谈谈对进程共享和线程安全的认识
* [ ] 谈谈对多进程开发的理解以及多进程应用场景
* [ ] 什么是协程
* [ ] 逻辑地址与物理地址，为什么使用逻辑地址
* [ ] Android 为每个应用程序分配的内存大小是多少
* [ ] 进程保活的方式
* [ ] 系统启动流程是什么
* [ ] 一个应用程序安装到手机上的过程发生了什么
* [ ] App 启动流程，从点击桌面开始（Activity 启动流程）
* [ ] 什么是 AIDL？解决了什么问题？如何使用
* [ ] Binder 机制及工作原理
* [ ] App 中唤醒其他进程的实现方式
* [ ] Activity、Window、View 三者的关系与区别
* [ ] ApplicationContext 和 ActivityContext 的区别
* [ ] ActivityThread，ActivityManagerService，WindowManagerService 的工作原理
* [ ] PackageManagerService 的工作原理
* [ ] PowerManagerService 的工作原理
* [ ] 权限管理系统（底层的权限是如何进行 grant 的）
* [ ] 操作系统中进程和线程有什么区别，系统在什么情况下会在用户态和内核态中切换
* [ ] 如果一个 App 里面有多个进程存在，请列举你所知道的全部 IPC 方法

[]()

* [ ] 如何对 Android 应用进行性能分析以及优化
* [ ] ANR 产生的原因是什么，怎么定位
* [ ] OOM 是什么，怎么解决，是否可以 try catch
* [ ] 内存泄露的解决方法
* [ ] ddms 和 traceView 的使用
* [ ] 性能优化如何分析 systrace
* [ ] 用 IDE 如何分析内存泄漏
* [ ] Java 多线程引发的性能问题，怎么解决
* [ ] 启动页白屏、黑屏、太慢怎么解决
* [ ] App 启动崩溃异常怎么捕捉
* [ ] 对于 Android App 闪退，可能有哪些原因，请针对每种情况简述分析过程
* [ ] 如何保持应用的稳定性
* [ ] RecyclerView 和 ListView 的性能对比
* [ ] Bitmap 如何处理大图，如何预防 OOM
* [ ] 如何缩小 Apk 的体积
* [ ] 如何统计启动时长

[]()

* [ ] 对热修复和插件化的理解
* [ ] 插件化原理分析
* [ ] 模块化实现（好处，原因）
* [ ] 项目组件化的理解
* [ ] 描述清点击 Android Studio 的 build 按钮后发生了什么


## React Native

[⇧ 返回顶部](#questions)

* [ ] 相对 iOS 和 Android 原生开发，React Native 有什么优点和缺点
* [ ] 描述下 React Native 组件的生命周期
* [ ] props 和 state 有哪些相同点和不同点
* [ ] 在 React Native 中，父组件和子组件是怎样通信的
* [ ] 在原生中，Bundle 是怎样加载的
* [ ] 当你调用 setState 时，背后会发生什么事情
* [ ] 如何在 React Native 中使用 Redux
* [ ] Redux 的状态管理流程是怎样的
* [ ] Redux 中同步 action 和异步 action 最大的区别是什么


## Network

[⇧ 返回顶部](#questions)

* [ ] 描述一次网络请求的流程
* [ ] TCP 中 3 次握手和 4 次挥手的过程
* [ ] TCP 与 UDP 的区别及应用
* [ ] HTTP 协议
* [ ] HTTP 1.0 与 2.0 的区别
* [ ] HTTP 报文结构
* [ ] HTTP 与 HTTPS 的区别以及如何实现安全性
* [ ] HTTPS 原理
* [ ] 谈谈你对 WebSocket 的理解
* [ ] WebSocket 与 socket 的区别
* [ ] 视频加密传输


## Data Structure & Algorithm

[⇧ 返回顶部](#questions)

* [ ] 简述常见的数据结构
* [ ] 堆的结构
* [ ] 树、B+ 树、二叉树、红黑树的了解
* [ ] 二叉树的深度优先遍历和广度优先遍历
* [ ] 堆和树的区别
* [ ] 图的了解

[]()

* [ ] 排序算法有哪些
* [ ] 最快的排序算法是哪个
* [ ] 手写冒泡排序
* [ ] 手写快速排序
* [ ] 快速排序的过程、时间复杂度、空间复杂度
* [ ] 手写堆排序

[]()

* [ ] 给阿里2万多名员工按年龄排序应该选择哪个算法
* [ ] GC算法(各种算法的优缺点以及应用场景)
* [ ] 蚁群算法与蒙特卡洛算法
* [ ] 子串包含问题(KMP 算法)写代码实现
* [ ] 一个无序，不重复数组，输出N个元素，使得N个元素的和相加为M，给出时间复杂度、空间复杂度，手写算法
* [ ] 万亿级别的两个URL文件A和B，如何求出A和B的差集C(提示：Bit映射->hash分组->多文件读写效率->磁盘寻址以及应用层面对寻址的优化)
* [ ] 两个不重复的数组集合中，求共同的元素
* [ ] 两个不重复的数组集合中，这两个集合都是海量数据，内存中放不下，怎么求共同的元素
* [ ] 一个文件中有100万个整数，由空格分开，在程序中判断用户输入的整数是否在此文件中，说出最优的方法
* [ ] 一张Bitmap所占内存以及内存占用的计算
* [ ] 2000万个整数，找出第五十大的数字
* [ ] 求1000以内的水仙花数以及40亿以内的水仙花数
* [ ] 烧一根不均匀的绳，从头烧到尾总共需要1个小时，现在有若干条材质相同的绳子，问如何用烧绳的方法来计时一个小时十五分钟呢
* [ ] 5枚硬币，2正3反如何划分为两堆然后通过翻转让两堆中正面向上的硬8币和反面向上的硬币个数相同
* [ ] 时针走一圈，时针分针重合几次


## Design

[⇧ 返回顶部](#questions)

* [ ] 谈谈你对 Android 设计模式的理解
* [ ] 项目中常用的设计模式有哪些
* [ ] 手写生产者-消费者模式
* [ ] 手写观察者模式
* [ ] 适配器模式、装饰者模式、外观模式的异同

[]()

* [ ] MVC、MVP、MVVM 原理和区别，请画出 MVC、MVP 的差异
* [ ] 从 0 设计一款 App 整体架构，如何去做
* [ ] 对于应用更新这块是如何做的 (解答：灰度，强制更新，分区域更新)



