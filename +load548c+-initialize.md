# +load和+Initialize

`+ load`

* * 当类和分类被添加到运行时时调用
  * 调用顺序：父类 &gt; 子类 &gt; 分类
  * 如果一个类和分类都实现了该方法，都会被调用
  * 默认情况下，每一个子类的该方法不会调用父类的方法
* `+ initializer`

  * 在一个类或者子类的类方法或者实例方法调用之前被调用

  * 调用顺序：父类 &gt; 子类 &gt; 分类

  * 每个类只调用一次，如果类和分类都实现了`+ initialize`方法，分类的实现被调用

  * 默认情况下，每一个子类的该方法会调用父类的方法

初始化的顺序

* 被引用的framework
* `+ load`

* \_\_attribute\_\_\(constructor\)

* 引用你的framework

* `+ initializer`



