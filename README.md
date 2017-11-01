# iOS-Interview

## [HIT-alibaba](https://hit-alibaba.github.io/interview/iOS/)

* +load
  * 当类和分类被添加到运行时时调用
  * 调用顺序：父类 &gt; 子类 &gt; 分类
* +initializer

  * 在一个类或者子类的类方法或者实例方法调用之前被调用

  * 调用顺序：父类 &gt; 子类 &gt; 分类

```
每个类只调用一次，如果类和分类都实现了+initialize方法，分类的实现被调用
```

初始化的顺序

```
被引用的framework

+ load方法

\_\_attribute\_\_\(constructor\)

引用你的framework

+ initializer方法
```



