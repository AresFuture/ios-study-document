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