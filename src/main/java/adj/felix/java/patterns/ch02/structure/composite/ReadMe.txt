01. 组合模式
	又称为合成模型模式、Composite模式。
	(1) 定义：将对象组合成树形结构, 以表示"整体-部分"的层次结构。
	(2) 目的：让用户能够以统一的接口处理单个对象以及对象组合。
	(3) 建模的概念
		1) 所涉及的群组既要你拿能包含单个个体, 还能包含集体群组。
		2) 需要定义出单个对象和对象组合的公共特
02. 角色
	(1) Component(抽象构件)：给参数组合的对象规定一个共有的接口, 及默认的行为。
	(2) Left(树叶构件)：参加组合的树叶对象, 该构件没有下级的子对象。
	(3) Composite(树枝构件)：提供管理和取得下层构件的行为方法。

03. 组合模式的两种形式
	根据所实现接口的区别分为：安全方式和透明方式。
	(1) 透明方式(Transparnet Conposite Pattern)
		Component声明用来管理子类对象的所有方法, 包括add()、remove()以及getChild()方法。
		优点：所有构件都有相同的接口。  即, 客户端可以同等地对待Left构件和Composite构件。
		缺点：不够安全, 因为Left构件和Composite构件在本质上是有区别的, 即Left构件根本没有子类对象。
	(2) 安全方式(Security Composite Pattern)
		Composite声明所有的用来管理子类对象的方法。
		优点：安全, 因为树叶类型的对象根本没有管理子类对象的方法。
		
04. 实用场景
	(1) 需要描述对象部分和整体的等级结构
	(2) 客户端必须平等对待所有的构件, 如Left和Composite组件。
	
05. 优缺点
	(1) 优点
		容易扩展新构件, 因为客户端无须知道构件是Left还是Composite类型。
	(2) 缺点
		组合模式是使用继承实现的, 很难扩展实现新的行为。