## UIView的常见属性

- NSArray * subViews
    - 所有子控件
    - 数组元素的顺序决定着子控件的显示层级顺序（下标越大，越在上面）

## UIView的常见方法
- addSubview:
    - 添加一个子控件
    - 使用这个方法添加的子控件会被塞到subViews数组的最后面
- 可以使用下面的方法调整子控件在subView数组中的顺序

```objc
// 将子控件view插入到subviews数组的index位置
- (void) insertSubView:(UIView *)view atIndex:(NSInteger) index;

// 将子控件view显示到子控件的下面
-(void) insertSubView:(UIView *）view belowSubview:(UIView *) subView;

// 将子控件view放到数组的最后面，显示在最上面
-(void)bringSubViewToFont:(UIView *) view;
// 将子控件view显示到子控件siblingSubview的上面
- (void)insertSubview:(UIView *)view aboveSubview:(UIView *)siblingSubview;

// 将子控件view放到数组的最前面，显示在最下面
-(void)sendSubViewToBack:(UIView *) view;

```