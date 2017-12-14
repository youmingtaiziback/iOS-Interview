# [iOS 关于MVC和MVVM设计模式的那些事](http://www.jianshu.com/p/caaa173071f3)

## MVC模式的缺陷

* 和理论中MVC模式不一致
  * Model：应该包括数据和操作数据的业务逻辑。实际中操作数据的业务逻辑会被放到Controller中
  * View：不应该直接引用Model
  * Controller：网络数据操作、本地数据操作等加重了Controller的臃肿程度

  * View和Controller耦合度过高



