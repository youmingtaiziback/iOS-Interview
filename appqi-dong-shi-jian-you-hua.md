# App启动时间优化

## [今日头条iOS客户端启动速度优化](https://techblog.toutiao.com/2017/01/17/iosspeed/)

t\(App总启动时间\) = t1\(main\(\)之前的加载时间\) + t2\(main\(\)之后的加载时间\)

* t1 = 系统dylib\(动态链接库\)和自身App可执行文件的加载

* t2 = main方法执行之后到AppDelegate类中的- \(BOOL\)Application:\(UIApplication \*\)Application didFinishLaunchingWithOptions:\(NSDictionary \*\)launchOptions方法执行结束前这段时间

## main\(\)调用之前的加载过程

App启动后的操作：加载可执行文件、加载dyld、dyld加载可执行文件依赖的动态链接库（包括系统的framework、加载Objective-C runtime的libobjc、libSystem）

App以Image为单位进行加载

