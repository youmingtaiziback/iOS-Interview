# [如何自己动手实现 KVO](http://tech.glowing.com/cn/implement-kvo/)

## KVO缺陷

* 监听只能走`-observeValueForKeyPath:ofObject:change:context:`方法，如果监听多个属性的话需要在该方法内部做判断
* 不支持自定义的selector或者block
* 父类和子类同时监听同一对象的同一属性时需要额外处理



