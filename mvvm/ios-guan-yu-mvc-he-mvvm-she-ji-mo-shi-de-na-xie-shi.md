# [iOS 关于MVC和MVVM设计模式的那些事](http://www.jianshu.com/p/caaa173071f3)

## MVC模式的缺陷

* 和理论中MVC模式不一致

  * Model：应该包括数据和操作数据的业务逻辑。实际中操作数据的业务逻辑会被放到Controller中
  * View：不应该直接引用Model
  * Controller：网络数据操作、本地数据操作等加重了Controller的臃肿程度

  * View和Controller耦合度过高

* 网络操作最重只能放在Controller里面，加重了Controller的臃肿程度

* 测试性较差

## MVVM（Model View View-Mode）

#### MVVM概念

* MVVM衍生于MVC，促进了UI代码与业务逻辑的分离
* 正式规范了视图和控制器紧耦合的性质
* 引入新的组件

![](/assets/import1.png)

#### MVVM 的使用建议

* MVVM 可以兼容你当下使用的MVC架构
* MVVM 增加你的应用的可测试性
* MVVM 配合一个绑定机制效果最好（PS：ReactiveCocoa你值得拥有）
* viewController 尽量不涉及业务逻辑，让 viewModel 去做这些事情
* viewController 只是一个中间人，接收 view 的事件、调用  viewModel 的方法、响应 viewModel 的变化
* viewModel 绝对不能包含视图 view（UIKit.h），不然就跟 view 产生了耦合，不方便复用和测试
* viewModel之间可以有依赖
* viewModel避免过于臃肿，否则重蹈Controller的覆辙，变得难以维护

#### MVVM 的优势

* 低耦合：View 可以独立于Model变化和修改，一个 viewModel 可以绑定到不同的 View 上
* 可重用性：可以把一些视图逻辑放在一个 viewModel里面，让很多 view 重用这段视图逻辑
* 独立开发：开发人员可以专注于业务逻辑和数据的开发 viewModel，设计人员可以专注于页面设计
* 可测试：通常界面是比较难于测试的，而 MVVM 模式可以针对 viewModel来进行测试





