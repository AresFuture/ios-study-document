# 自定义控件注意点

- 一个控件有2种创建方式

## 通过代码创建
- 初始化一定会调用initWithFrame:方法

## 通过xib\storyBoard创建
- 初始化不会调用initWithFrame:方法，只会调用initWithCoder:方法
- 初始化完毕后调用awakeFromNib方法

### 有时候希望在控件初始化时做一些初始化操作，比如添加子控件、设置基本属性
### 这时需要根据控件的创建方式，来选择在initWithFrame:、initWithCoder:、awakeFromNib的哪个方法中操作
