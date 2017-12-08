# [Key-Value Observing Done Right](https://www.mikeash.com/pyblog/key-value-observing-done-right.html)

## KVO缺点

#### `-addObserver:forKeyPath:options:context:`不能传递自定义的selector

NSNotificationCenter注册一个监听者时可以传递自定义selector，这样有利于把子类的业务逻辑和父类区分开。但在KVO中，子类和父类都必须在-observeValueForKeyPath:ofObject:change:context:中进行处理，如果子类和父类都监听了同一个对象的同一个属性，还需要判断是调用子类还是父类的处理逻辑

#### context参数作用不大

context只能用来标识父类对本次的通知是否感兴趣，别无它用

