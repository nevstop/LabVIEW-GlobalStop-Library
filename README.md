# LabVIEW GlobalStop Library

提供给系统使用的全局停止方案。

使用Function Global Variable （FGV）的方式，存储一个Boolean 类型的标志数据，不同线程通过读取该FGV判断是否需要停止。

![Library Pallette](https://cloud.githubusercontent.com/assets/8196752/10752145/8288f624-7cc1-11e5-9700-e3740e08f571.png)

- `Init.vi` : 初始化STOP FGV，如果ERROR 发生，则全局停止位初始化为 TRUE
- `Reset.vi` :设置STOP FGV为 False，Index 标识模块编号，-1 标识全局停止位
- `Set.vi` : 设置STOP FGV为 True，Index 标识模块编号，-1 标识全局停止位
- `Get.vi` :检查STOP FGV值，如果输入的错误簇为False，会自动调用Set.vi 方法，Index 标识模块编号，-1 标识全局停止位
- `CheckSet.vi` :检查输入的Boolean值，（通常连接到Stop Button上）判断是否需要退出。如果输入的错误簇为False，会自动调用Set.vi 方法，Index 标识模块编号，-1 标识全局停止位

优点：简单、高效、易用，STOP FGV的方案也保证了多线程安全。
