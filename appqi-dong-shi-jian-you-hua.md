# App启动时间优化

## [今日头条iOS客户端启动速度优化](https://techblog.toutiao.com/2017/01/17/iosspeed/)

t\(App总启动时间\) = t1\(main\(\)之前的加载时间\) + t2\(main\(\)之后的加载时间\)

* t1 = 系统dylib\(动态链接库\)和自身App可执行文件的加载

* t2 = main方法执行之后到AppDelegate类中的- \(BOOL\)Application:\(UIApplication \*\)Application didFinishLaunchingWithOptions:\(NSDictionary \*\)launchOptions方法执行结束前这段时间

## main\(\)调用之前的加载过程

App启动后的操作：加载可执行文件、加载dyld、dyld加载可执行文件依赖的动态链接库（包括系统的framework、加载Objective-C runtime的libobjc、libSystem）

App以Image为单位进行加载

#### 什么是image

* executable
* dylib、framework
* bundle 资源文件，只能用dlopen加载，不推荐使用

#### 系统使用动态链接有几点好处

* 代码共用
* 易于维护
* 减少可执行文件体积

#### 什么是ImageLoader

ImageLoader把image加载到内存，每一个image对应一个ImageLoader。每一个image包括编译后的符号和代码

加载顺序

* 将动态链接的image递归加载
* 从可执行文件image递归加载所有符号

#### 动态链接库加载的具体流程

* load dylibs image
  * 步骤
    * 分析所依赖的动态库
    * 找到动态库的mach-o文件
    * 打开文件
    * 验证文件
    * 在系统核心注册文件签名
    * 对动态库的每一个segment调用mmap\(\)
  * 可优化的点
    * 减少非系统库的依赖
    * 合并非系统库
    * 使用静态资源，比如把代码加入主程序
* Rebase image
* Bind image
* Objc setup
* initializers



