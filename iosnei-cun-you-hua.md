# [微信读书 iOS 性能优化总结](https://wereadteam.github.io/2016/05/03/WeRead-Performance/)

## 如何发现性能问题 {#如何发现性能问题}

从两个维度进行了监控

* 业务性能监控，是指在App本地，业务的开始和结束处打点上报，然后后台统计达到监控目的
* 卡顿监控。卡顿监控的实现一般有两种方案

  * 主线程卡顿监控

  * FPS监控

## 性能问题的解决方法 {#性能问题的解决方法}

#### 优化业务流程 {#1-优化业务流程}

#### 合理的线程分配 {#2-合理的线程分配}

#### 预处理和延时加载 {#3-预处理和延时加载}

#### 缓存 {#4-缓存}

## 如何预防性能问题 {#如何预防性能问题}

#### 内存泄露检测工具 {#1-内存泄露检测工具}

#### FPS/SQL性能监测工具条 {#2-FPS-SQL性能监测工具条}

#### UI / DataSource主线程检测工具 {#3-UI-DataSource主线程检测工具。}

#### 排版引擎自动化检测工具 {#4-排版引擎自动化检测工具}

#### 书源检测工具 {#5-书源检测工具}

# [微信读书 iOS 质量保证及性能监控](http://wereadteam.github.io/2016/12/12/Monitor/)

## 对网络层成功率的监控 {#对网络层成功率的监控}

## 数据层的性能监控 {#数据层的性能监控}

## UI数据源监控 {#UI数据源监控}

## UI主线程监控 {#UI主线程监控}

#### 防止子线程访问UI

hook掉UIView、CALayer的setNeedsLayout、setNeedsDisplay、setNeedsDisplayInRect:三个方法

#### FPS监控

[demo](https://github.com/featuretower/GYMonitor)

#### 线上用户监控



