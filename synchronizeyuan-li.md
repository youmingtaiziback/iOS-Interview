# [深入理解 iOS 开发中的锁](https://bestswifter.com/ios-lock/)

## 摘要

本文要做的就是简单的分析 iOS 开发中常见的几种锁如何实现，以及优缺点是什么，为什么会有性能上的差距，最终会简单的介绍锁的底层实现原理![](/assets/1171077-280edff700291835.png)加解锁速度不表示锁的效率，只表示加解锁操作在执行时的复杂程度

## OSSpinLock

不安全，可能发生优先级反转，高优先级线程忙等

#### 自旋锁的实现原理

```
bool lock = false; // 一开始没有锁上，任何线程都可以申请锁
do {
    while(lock); // 如果 lock 为 true 就一直死循环，相当于申请锁
    lock = true; // 挂上锁，这样别的线程就无法获得锁
        Critical section  // 临界区
    lock = false; // 相当于释放锁，这样别的线程可以进入临界区
        Reminder section // 不需要锁保护的代码        
}
```

但是要确保申请锁的过程是原子操作

# [关于 @synchronized，这儿比你想知道的还要多](http://yulingtianxia.com/blog/2015/11/01/More-than-you-want-to-know-about-synchronized/)

# 



