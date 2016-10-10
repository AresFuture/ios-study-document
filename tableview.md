- TableView如何显示数据
    - 设置dataSource数据源
    - 数据源遵守UITableViewDataSource协议
    - 数据源要实现协议中的某些方法
    
```objc
 - (NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section;

// Row display. Implementers should *always* try to reuse cells by setting each cell's reuseIdentifier and querying for available reusable cells with dequeueReusableCellWithIdentifier:

// Cell gets various attributes set automatically based on table (separators) and data source (accessory views, editing controls)
- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath;

    ```
## TableView - Cell的循环利用方式1

```objc
/**
 * 什么时候调用：每当一个cell进入视野范围内就会调用
 */
-(UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath{

 // 1.创建cell
 static NSString* Identifier = @"identifier";
 UITableViewCell* cell = [tableView dequeueReusableCellWithIdentifier:Identifier];

 if (cell == nil) {
 cell = [[UITableViewCell alloc] initWithStyle:UITableViewCellStyleSubtitle reuseIdentifier:Identifier];
}

 // 2.设置cell数据
 return cell;

}

```

## TableView - Cell的性能优化

```objc// 定义重用标识NSString *ID = @"cell";```

- 注册某个标识对应的cell类型

```objc// 在这个方法中注册cell- (void)viewDidLoad { [super viewDidLoad];

 // 注册某个标识对应的cell类型 [self.tableView registerClass:[UITableViewCell class] forCellReuseIdentifier:ID];}```
