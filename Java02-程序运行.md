## Task1.单文件代码结构

1、可以看到，这份代码被分成了四个部分，请尝试解释每个部分，回答什么是包（pakage），包的作用是什么，什么是main函数，并总结出一个单文件java程序的基本结构。

### 代码的四个部分解释：

1. **包声明 (`package com.Example;`)**：
   - **定义**：包是Java中组织类的一种方式。
   - **作用**：避免命名冲突，便于管理和引用。
2. **导入语句 (`import com.Example.tool.Print;`)**：
   - **定义**：引入其他包中的类或接口。
   - **作用**：使当前文件可以使用外部包中的功能。
3. **主类 (`public class HelloWorld { ... }`)**：
   - **定义**：包含 `main` 方法的类，程序入口点。
   - **`main` 函数**：程序启动时执行的方法，格式为 `public static void main(String[] args)`。
4. **辅助类 (`class Test { ... }`)**：
   - **定义**：在同一文件中定义的其他类。
   - **作用**：提供额外的功能支持。

### 单文件Java程序的基本结构：

![image-20250916164030087](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250916164030087.png)

总结：包用于组织类，导入语句引入外部功能，主类包含 `main` 方法作为程序入口，辅助类提供额外支持。



2、在运行程序时，可以给程序传入参数，由main函数的args参数接收，请你更改main函数，使用命令行或者IDEA运行这个程序传入“111 222 333”这三个参数，并在main函数中打印出来。

![image-20250916181332261](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250916181332261.png)

## Task2.多文件Java项目

3、在你本地的IDEA中创建上述结构的java项目，HelloWorld.java文件的内容前面已经给出，现在请你写出Print.java文件中的代码，使得该Java项目能正常运行并打印出“Hello World”。

![main](https://tongyi-main.oss-accelerate.aliyuncs.com/upload/20250916/5bc5807465618d2e2581803b6a4b3e5d/9fa7d0e90d3a4716921c9bd399bbd47c/image.png?Expires=1821088913&OSSAccessKeyId=LTAI5tL97mBYzVcjkG1cUyin&Signature=8jQHk18Qwu9NmWXbQeckjJ0SZwI%3D)