# KVO缺陷

## 监听时`-addObserver:forKeyPath:options:context:`

不能传递自定义的selector或者block

context参数只能用来区分父类或者子类感兴趣的监听，作用受限

## 回调时`-observeValueForKeyPath:ofObject:change:context:`

## 移除时`-removeObserver:forKeyPath:`



