# 什么是堆污染 

先来看一段代码：

```Java
public class Test {
    public static void main(String[] args) {
        // List<Integer> list = new ArrayList<>();
        // list.add(20);

        List list = new ArrayList<Integer>();
        // Unchecked call to 'add(E)' as a member of raw type 'java.util.List'
        list.add(20);

        // 下面代码引起"未经检查的转换"警告，编译、运行时完全正常
        List<String> ls = list;
        // 但只要访问 ls 里的元素，就会引起运行时异常
        System.out.println(ls.get(0));
    }
}
```
```
Exception in thread "main" java.lang.ClassCastException: java.lang.Integer cannot be cast to java.lang.String
	at Test.main(Test.java:12)
```

Java 把引发这种错误的原因成为「堆污染」(Heap pollution)：
* 当把一个不带泛型的对象赋给一个带泛型的变量时，往往就会发生这种堆污染（如上述例子）。
* 对于形参个数可变的方法，该形参的类型又是泛型，将更容易导致堆污染（如下面例子）。

```Java
public class Test {
    public static void main(String[] args) {
        faultyMethod(new ArrayList<>());
    }

    public static void faultyMethod(List<String>... listStrArray) {
        // Java 不允许创建泛型数组，因此 listArray 只能被当成 List[] 处理
        // 此时相当于把 List<String> 赋给了 List, 已经发生了堆污染
        List[] listArray = listStrArray;
        List<Integer> myList = new ArrayList<>();
        myList.add(new Random().nextInt(100));
        listArray[0] = myList;
        // Error
        String s = listStrArray[0].get(0);
    }
}
```
