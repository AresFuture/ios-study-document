## 九宫格计算思路
- 利用控件的索引index计算出控件所在的行号和列号
- 利用列号计算控件的x值
- 利用行号计算控件的y值

## HUD
- 其他说法：指示器、遮盖、蒙版
- 半透明HUD的做法
    - 背景设置为班透明颜色

## 定时任务
- 方法1：performSelector

```objc
[self performSelector@selector(hideHud) withObject afterDelay:1.5];
```

- 方法2：GCD

```objc
 dispatch_after(dispatch_time(DISPATCH_TIME_NOW, (int64_t)(1.5 * NSEC_PER_SEC)), dispatch_get_main_queue(), ^{

 self.hud.alpha = 0.0;

 });

```

- 方法3：NSTimer

```objc
[NSTimer scheduledTimerWithTimeInterval:1.5 target:self selector:@selector(hideHUD) userInfo:nil repeats:NO];
// repeats如果为YES，意味着每个1.5S都会调用一次self的hidHUD方法
```

## 常见问题
- 项目里面的某个.m文件无法使用
    - 检查：BuildPhases -> Compile Sources
- 项目里面的某个资源文件（比如plist、音频等）无法使用
    - 检查：BuildPhases -> Copy Bundle Resources

## 模型
- 什么是模型？
    - 专门用来存储数据的对象
    - 一般都是一些直接继承自NSObject的纯对象
    - 内部会提供一些属性来存放数据
   
## 一个控件看不见有哪些可能？
  - 宽度或者高度为0
  - 位置不对（比如是个负数或者超大的数，已经超出屏幕）
  - hidden == YES
  - alpha <= 0.01
  - 没有设置背景色，没有设置内容
  - 可能是文字和背景色一样
 