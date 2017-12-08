# KVO缺陷

## 监听时`-addObserver:forKeyPath:options:context:`

不能传递自定义的selector或者block

context参数只能用来区分父类或者子类感兴趣的监听，作用受限

## 回调时`-observeValueForKeyPath:ofObject:change:context:`

所有的监听都必须走此方法，代码量剧增

需要在此方法中考虑父类是否对本次通知感兴趣的情况

## 移除时`-removeObserver:forKeyPath:`

没有携带足够的参数信息，不能做到只删除子类或者父类的监听



