## Task1.集合

**引入：你知道什么是集合吗?它和数组有什么相同点和不同点呢?既然有了数组 为什么还需要集合呢?**

集合是存储一组不重复元素的数据结构。

**相同点**：都用于存储数据。

**不同点**：

- 数组有固定大小，集合大小可变。
- 数组元素类型一致，集合可以存储不同类型。
- 集合自动去重，数组允许重复。

需要集合是因为它更灵活，支持动态增删和自动去重，适合处理不确定数量或类型的数据。



**Q1. 请你简单了解一下上面的集合接口以及实现类 简单的说一说他们各自的功能 并概括一下数组与集合的区别**

**集合接口及实现类功能：**

- **Collection**：基本集合接口，包含 List 和 Set。
  - **List**（ArrayList, LinkedList）：有序、可重复元素的集合。
    - **ArrayList**：基于数组，随机访问快，插入删除慢。
    - **LinkedList**：基于链表，插入删除快，随机访问慢。
  - **Set**（HashSet, TreeSet）：无序、不可重复元素的集合。
    - **HashSet**：基于哈希表，存取速度快。
    - **TreeSet**：基于红黑树，自动排序。
- **Map**（HashMap, TreeMap）：键值对存储。
  - **HashMap**：基于哈希表，存取速度快。
  - **TreeMap**：基于红黑树，按键自动排序。

**数组与集合的区别：**

- **数组**：固定大小，类型一致，支持随机访问。

- **集合**：动态大小，类型灵活，提供多种操作方法。

  

## Task2.遍历

**1.增强for循环( 又称for-each循环 )**

**Q2. 请你用增强for循环遍历list中的元素 依次打印出结果 给出你的代码和运行结果截图**

![image-20250921175803585](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921175803585.png)

**2.forEach方法**

**Q3. 什么是匿名内部类 什么是函数式接口? ( 感兴趣的同学可以去了解一下四大函数式接口 体会一下OOP和FP的区别 ) 把上面的遍历代码用lambda表达式改写 给出你的代码和运行结果截图 并总结一下lambda表达式的用法**

**匿名内部类**：在 Java 中，当你需要创建一个类的实例但不需要为这个类命名时，可以使用匿名内部类。它通常用于实现接口或抽象类，并且只使用一次。

**函数式接口**：是一个只有一个抽象方法的接口。Java 8 引入了 `@FunctionalInterface` 注解来标记这样的接口。常见的函数式接口有 `Runnable`、`Callable`、`Comparator` 和 `Consumer` 等。

**用lambda表达式改写:**![image-20250921180534334](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921180534334.png)

##### **总结 lambda 表达式的用法**:

##### Lambda 表达式的优点：

1. **简洁性**：lambda 表达式使得代码更加简洁明了，减少了冗余的代码量。
2. **可读性**：通过 lambda 表达式，代码的意图更加清晰，易于理解和维护。
3. **函数式编程支持**：lambda 表达式是 Java 8 引入的重要特性之一，支持函数式编程风格，使得代码更加灵活和强大。

##### Lambda 表达式的语法结构：

- **参数列表**：lambda 表达式的参数列表在箭头（`->`）的左边，可以省略参数类型。

- **箭头操作符**：`->` 是 lambda 表达式的标志，表示参数列表和主体之间的分隔。

- **主体**：箭头右边是 lambda 表达式的主体，可以是一个表达式或一个代码块。

  

##### 3.迭代器遍历

![image-20250921181109645](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921181109645.png)

![image-20250921181124237](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250921181124237.png)



## Task3.泛型

**Q4. 请你完成下面的模拟项目**

- 创建一个泛型接口 该接口是一个仓库 要求能够储存任何类型的数据 ( 使用泛型 )

- 这个接口内有两个方法 save( ) 方法用于向仓库中添加数据 getById( ) 方法用来根据id获取数据
- 创建MyRepository类 实现上面的接口 完成上述两个方法的具体实现 ( 注意 id是整数类型 从0开始自增 是数据的唯一标识 )
- 提示: 可以使用hashMap

给出下述User类

- 要求分别在你的MyRepository储存String User Integer类型的三组数据 并调用你写的遍历方法 在main函数中打印出仓库中所有元素的内容 给出你的完整代码 以及输出截图

  ![image-20250927152316440](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927152316440.png)![image-20250927152343639](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927152343639.png)![image-20250927152404186](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927152404186.png)![image-20250927152421568](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927152421568.png)

## Task4.练习

**Q5. 给出下面模拟案例的代码和运行结果截图**

![image-20250927153658673](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927153658673.png)

![image-20250927153721184](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927153721184.png)

![image-20250927153729585](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927153729585.png)