## 数据刷新方法
- 重新刷新屏幕上的所有cell<br>

```objc
[self.tableView reloadData];
```
- 刷新特定行的cell<br>
```objc
[self.tableView reloadRowsAtIndexPaths:@[NSIndexPath indexPathForRow:0 inSection:0],[NSIndexPath indexPathForRow:1 inSection:0] withRowAnimation:UITableViewRowAnimationLeft];
```