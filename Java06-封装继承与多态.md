## Task1.继承

1、请注意，java并不支持多继承，这是为什么？

java不支持多继承是为了避免“菱形问题”（Diamond Problem），即当一个子类从两个父类继承时，如果这两个父类有同名方法，子类在调用该方法时会不清楚应该调用哪个父类的方法，从而导致歧义和复杂性。通过只允许单继承，Java简化了类的层次结构，减少了潜在的冲突和维护难度。

## Task2.多态

2、你知道`@Override`吗，他负责在子类重写父类的方法来实现不同类的运算逻辑，请完成以下问题：

对几何图形进行建模并完成圆，三角形，矩形的周长，面积计算

其实还有另一种做法，使用接口来完成，请你给出使用接口的解答

![image-20250921172557634](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921172557634.png)

![image-20250921172642381](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921172642381.png)

![image-20250921172650578](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921172650578.png)![image-20250921172658752](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921172658752.png)![image-20250921172719036](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921172719036.png)



## Task3.封装

3、请你说明public,private等关键词的用法，并完成以下代码。

### 访问修饰符的用法

- **`public`**：公共的，表示该成员可以在任何地方被访问。
- **`private`**：私有的，表示该成员只能在定义它的类内部被访问。
- **`protected`**：受保护的，表示该成员可以在同一个包内或子类中被访问。



![image-20250921173233121](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921173233121.png)

![image-20250921173248661](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921173248661.png)![image-20250921173258879](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921173258879.png)![image-20250921173314063](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921173314063.png)![image-20250921173322601](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921173322601.png)
