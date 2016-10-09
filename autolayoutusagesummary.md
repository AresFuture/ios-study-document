## 使用代码实现AutoLayout的方法1

* 创建约束

```objc
+(id)constraintWithItem:(id)view1 attribute:(NSLayoutAttribute)attr1 relatedBy:(NSLayoutRelation)relation toItem:(id)view2 attribute:(NSLayoutAttribute)attr2 multiplier:(CGFloat)multiplier constant:(CGFloat)c;

* view1 ：要约束的控件
* attr1 ：约束的类型（做怎样的约束）
* relation ：与参照控件之间的关系
* view2 ：参照的控件
* attr2 ：约束的类型（做怎样的约束）
* multiplier ：乘数
* c ：常量
```

* 添加约束

```objc
- (void)addConstraint:(NSLayoutConstraint *)constraint;

- (void)addConstraints:(NSArray *)constraints;
```

* 注意：

  * 一定要在拥有父控件之后再添加约束
  * 关闭Autoresizing功能

    ```objc
    view.translatesAutoresizingMaskIntoConstraints = NO;
    ```



## 使用代码实现AutoLayout的方法2 - VFL

* 使用VFL创建约束数组

```objc
+ (NSArray *)constraintsWithVisualFormat:(NSString *)format options:(NSLayoutFormatOptions)opts metrics:(NSDictionary *)metrics views:(NSDictionary *)views;

* format ：VFL语句
* opts ：约束类型
* metrics ：VFL语句中用到的具体数值
* views ：VFL语句中用到的控件

```

## 使用代码实现AutoLayout的方法3 - Masonry

- 使用步骤
    - 添加Masonry文件夹的所有源文件到项目中
    - 添加2个宏，导入主头文件
    ```objc
    #define MAS_SHORTHAND
    #define MAS_SHORTHAND_GLOBALS
    #import "Masonry.h"

    ```

- 添加约束的方法

```objc
 // 这个方法只会添加新的约束
 [blueView makeConstraints:^(MASConstraintMaker *make) {

 }];

 // 这个方法将以前的约束删除，添加新的约束
 [blueView remakeConstraints:^(MASConstraintMaker *make) {

 }];

 // 这个方法将会覆盖以前的某些特定约束
 [blueView updateConstraints:^(MASConstraintMaker *make) {

 }];
```

- 约束的类型
```objc

```
