## storybord 的认识
- 用来描述软件界面
- 默认情况下，程序一启动会加载Main.StoryBoard
- 加载storyBoard时，会首先创建和实现箭头所指的控制器面板

## IBAction 和 IBOutlet

- IBAction
    - 本质就是void
    - 能让方法具备连线功能
- IBOutlet
    - 能让属性具备连线功能

## storyBoard 容易出现的问题
- 被连接的方法代码被删掉，但是连线没有去掉
    - 可能会出现方法找不到错误
    - unrecognized selector sent to instance

- 被连接的属性代码被删掉，但是连线没有去掉
    - setValue:forUndefinedKey:] this class is not key value coding-compliant for the key

## UIViewController(控制器)的认识

- 一个控制器负责管理一个大界面
- 控制器负责界面的创建、事件处理等

## 类扩展
- 格式

```
@interface className(){
}
/** 属性、方法的声明 */
@end
```