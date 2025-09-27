## Task1.异常

**Q1. 请你简单概述一下Error与Exception的区别 当发生Exception和Error时 程序的处理态度分别应该是什么?**

1.区别：

- **Error** 是严重错误，通常表示程序无法恢复的系统级问题（如虚拟机崩溃、内存溢出），应由 JVM 处理，程序一般不捕获。

- **Exception** 是可预期的异常情况（如文件不存在、除零），程序应主动处理或声明抛出。

  **区别本质**：Error 是“灾难性”事件，超出程序控制范围；Exception 是“可处理”的逻辑错误，程序员可通过 try-catch 或 throws 机制应对。

2.处理态度：

- 对于 Exception，应该**主动处理**（try-catch）或**声明抛出**（throws），保证程序健壮性。
- 对于 Error，通常**无需处理**，因为其发生时程序已处于不稳定状态，继续运行可能造成更大风险。

3.心得：

异常处理不仅是技术手段，更是对程序稳定性和用户体验的保障。区分 Error 和 Exception，能帮助我们更合理地分配精力去“预防”和“修复”。

**Q2. 你知道这两种异常有什么区别吗 他们发生的原因分别是什么?**

- **Checked 异常**：编译时检查，必须处理（try-catch 或 throws），如 `IOException`。原因：外部环境问题（如文件不存在、网络中断）。

- **Unchecked 异常**：运行时异常，不强制处理，如 `NullPointerException`、`ArithmeticException`。原因：程序逻辑错误（如空指针、除零）。

  心得：合理使用两种异常类型，能体现对“可控”与“不可控”风险的认知。开发者应主动处理 Checked 异常，避免 Unchecked 异常的发生，让程序既安全又高效。

## Task2.处理

**Q3. 题目: 文件读取和数据处理**

编写一个Java程序，要求完成以下功能：1.读取文件；2.数据处理；3.异常处理；

![image-20250927172727939](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927172727939.png)![image-20250927172753481](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927172753481.png)![image-20250927172811632](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927172811632.png)

## Task3.Stream流

**Q4. 尝试执行上面代码 会得到什么结果? 这和你预想的一样吗? 为什么会出现这种结果?**

![image-20250927174625109](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927174625109.png)

为什么出现这种结果？

- `System.out.println(limit)` 打印的是 `Stream` 对象本身，而不是它的内容。

- `limit(4)` 是**中间操作**，不会立即执行。

- 只有调用 `forEach`、`collect`、`count` 等**终结方法**时，才会触发流的真正处理。

  （心得：Stream 是“懒加载”的，只有终结方法才会真正执行。记住：**没有终结方法，流就不会动！**）

**Q5. 完成下述题目**

定义一个学生类、初始代码![image-20250927180045689](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927180045689.png)![image-20250927180100473](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927180100473.png)![image-20250927180110670](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927180110670.png)