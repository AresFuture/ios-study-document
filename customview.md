# 自定义控件注意点

- 一个控件有2种创建方式

## 通过代码创建
- 初始化一定会调用initWithFrame:方法

## 通过xib\storyBoard创建
- 初始化不会调用initWithFrame:方法，只会调用initWithCoder:方法
- 初始化完毕后调用awakeFromNib方法

