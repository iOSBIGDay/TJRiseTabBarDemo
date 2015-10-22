# TJRiseTabBarDemo

# Overview
**TJRiseTabBarDemo** 包含自定义 **TabBar** ,  **拦截系统返回函数**

# Demo 1 
收集自微博上看到的 [@我的眼里只有代码](http://weibo.com/fuckingcode)，根据个人理解稍作封装、修改、优化。这里是 [原工程地址](https://github.com/NoCodeNoWife/LLRiseTabBar-iOS)

![view demo](https://github.com/devtofu/TJRiseTabBarDemo/blob/master/TJRiseTabBarDemo/ScreenShot/home.png?raw=true)

#### Basic Usage
1、共3个类`LLTabBar` `LLTabBarItem` `TJTabbarController`，图标名称的修改写在 **TJTabbarController** 

2、设置 `self.window.rootViewController = tabbarController`

# Demo 2
收集自 [Dashing_Pro](http://www.jianshu.com/users/9e4ad2be1304/latest_articles) 简书上的一篇文章 [原文地址](http://www.jianshu.com/p/6376149a2c4c)，非常好的想法，通过一些手段将系统navigationBar的pop代理开放出来，替换成自己的实现，达到监听返回点击事件的效果。

#### Basic Usage
1、遵守定义的协议```<YYNavigationControllerShouldPopProtocol>```
  
  
2、实现```-(BOOL)yy_navagationControllerShouldPopWhenSystemBackItemClick:```协议，返回 **NO**

```
-(BOOL)yy_navagationControllerShouldPopWhenSystemBackItemClick:(TJNavigationController *)navigationController{
    
    [[[UIAlertView alloc] initWithTitle:nil
                                message:@"我就问你，确定要返回吗？"
                               delegate:self
                      cancelButtonTitle:@"取消"
                      otherButtonTitles:@"确定", nil]
     show];
    
    return NO;
}
```
but 这里有个问题，滑动返回并不会触发这个函数，原文有实现，以后在增加。

![view demo](https://github.com/devtofu/TJRiseTabBarDemo/blob/master/TJRiseTabBarDemo/ScreenShot/screenshot.gif?raw=true)


# License

本 Demo 只作为收集好的开源工具集成在一起体验应用在项目中的效果，请尊重原作者。