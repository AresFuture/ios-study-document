## 屏幕适配的发展历史- iPhone3GS\iPhone4 - 没有屏幕适配可言 - 全部用frame、bounds、center进行布局 - 很多这样的现象：坐标值、宽度高度值全部写死```objcUIButton *btn1 = [[UIButton alloc] init];btn1.frame = CGRectMake(0, 0, 320 - b, 480 - c);```

- iPad出现、iPhone横屏 - 出现Autoresizing技术 - 让横竖屏适配相对简单 - 让子控件可以跟随父控件的行为自动发生相应的变化 - 前提是：关闭Autolayout功能 - 局限性 - 只能解决子控件跟父控件的相对关系问题 - 不能解决兄弟控件的相对关系问题

- iOS 6.0（Xcode4）开始 - 出现了Autolayout技术 - 从Xcode5.0(iOS 7.0)开始，开始流行Autolayout
