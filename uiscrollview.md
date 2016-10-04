## UIScrollView的基本使用
- 将需要展示的内容添加到UIScrollView中
- 设置UIScrollView的contentSize属性，告诉UIScrollView所有内容的尺寸，也就是告诉它滚动的范围（能滚多远，滚到哪里是尽头）

- UIScrollView显示内容的小细节
    - 超出UIScrollView边框的内容被自动隐藏
    - 用户可以用过手势拖动来查看超出边框并被隐藏的内容

## UIScrollView无法滚动的解决方法
- 如果UIScrollView无法滚动，可能有如下原因：
    - 没有设置contentSize
    - scrollEnabled=NO
    - 没有接受到触控事件：userInteractionEnabled=NO

## UIScrollView的常见属性
- @property（nonatomic）CGPoint contentOffset;
    - 这个属性用来表示UIScrollView滚动的位置（内容左上角与scrollView左上角的间距值）
- @property（nonatomic）CGSize contentSize;
    - 这个属性用来表示UIScrollView的内容尺寸，滚动范围（能滚多远）

- @property（nonatomic）UIEdgeInsets contentInsert;
    - 这个属性能够在UIScrollView的4周增加额外的滚动区域，一般用来避免scrollView的内容被其他空间挡住