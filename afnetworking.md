# [AFNetworking源码分析](http://www.jianshu.com/p/8eac5b1975de)

## 简述

本篇文章只涉及了与操作队列，多线程相关的分析

## NSURLConnection的简单使用

同步异步调用

使用block或者代理

多处调用时造成的问题

* 软件结构不清晰，没有剥离出网络层

* 没有实现网络请求统一管理，无法实现取消所有网络请求等功能

* 会出现很多重复的代码，没有让公用功能形成模块，进行复用

## 使用NSURLConnection版本的AFNetworking

使用网络框架的好处在于可以将分散在各个视图控制器中的网络请求统一起来模块化形成网络层，降低与数据层和表现层的耦合

基于NSURLConnection的AFNetworking是只创建了一条线程来发起所有请求并阻塞以等待响应

## 重构推出的NSURLSession解决了NSURLConnection哪些问题

NSURLConnection只隐藏了单个网络请求的线程的相关操作，并没有提供接口来解决多个网络请求时多个线程的管理问题，譬如当有多个网络请求时是否应该使用线程池来避免不停创建与销毁线程（这个可以有NSOperationQueue很好的解决）

NSURLConnection不是基于HTTP/2协议的，若使用NSURLConnection发起请求则每次请求都需要经过三次握手过程

## 基于NSURLSession的AFNetworking的源码分析

# [从 NSURLConnection 到 NSURLSession](https://objccn.io/issue-5-4/)

  




