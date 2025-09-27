## Task1.字节流

**Q1. 设计一个程序 实现功能: 将doro.jpg复制一份到项目根目录下 新图片命名为doro_copy.jpg**

![image-20250927190825838](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927190825838.png)

![image-20250927190844841](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927190844841.png)![image-20250927190904892](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927190904892.png)

思考：

1. **I/O 操作是编程的基础能力之一**

   文件读写不仅是技术操作，更是理解计算机如何处理数据的关键。

   字节流是所有二进制数据传输的基础，图像、音频、视频都依赖它。

2. **缓冲机制的重要性**

   不要小看 `byte[]` 的使用，它能极大提升性能。

   在实际开发中，很多框架（如 NIO、Netty）都基于缓冲优化设计。

3. **资源管理必须严谨**

   忘记关闭流会导致文件锁住、内存泄漏等问题。

   使用 `try-with-resources` 是最佳实践，推荐在所有 I/O 操作中使用。

4. **不要被“文件类型”迷惑**

   jpg` 是二进制文件，不能用文本编辑器打开，但可以用字节流正确复制。

   所有文件在底层都是字节流，Java 的 I/O 模型统一而强大。

5. **动手实践才能真正掌握**

   只看书不会写，只有自己敲代码、调试错误，才能理解每个细节。

## Task2.字符流

**Q2. 设计一个程序: 读取name.txt 将表中的人名按照unicode自然排序 每个人名占据一行 在项目根目录下创建name_sorted.txt文件 将排序后的内容写入name_sorted.txt文件 要求去掉多余的首尾空格与空行**

![image-20250927191828731](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927191828731.png)![image-20250927191840714](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927191840714.png)![image-20250927191919057](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927191919057.png)![image-20250927191906852](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927191906852.png)

心得：

1. **字符流 vs 字节流**

   字节流适合处理图片、音频、二进制数据。

   字符流更适合处理文本，能自动处理编码问题，避免乱码。

2. **编码的重要性**

   同一份字节数据，用不同编码解析会得到不同结果。

   必须显式指定编码（如 UTF-8），才能保证正确性。

3. **流的封装层次清晰**

   先创建底层字节流（`FileInputStream`）

   再转换为字符流（`InputStreamReader`）

   最后加缓冲（`BufferedReader`）

   层层封装，功能逐步增强。

4. **资源管理要规范**

   使用 `try-with-resources` 自动关闭所有流。

   外层流关闭时，内部包裹的流也会自动关闭（链式关闭机制）。

5. **编程细节决定成败**

   一个 `trim()` 能解决空行问题；

   一个 `newLine()` 能避免跨平台问题；

   一个正确的编码设置能避免乱码灾难。

## Task3.序列化与反序列化

**Q3. 用上面的代码 创建一个student对象 使用序列化将该对象的信息储存在项目文件根目录下的student.dat文件中 再使用反序列化将数据赋值给新的Student对象doro 最后输出doro的信息 ( Student的toString方法已重写好了 )**

![image-20250927192650970](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927192650970.png)

![image-20250927192709247](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927192709247.png)

![image-20250927192718020](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927192718020.png)

![image-20250927192725497](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927192725497.png)

![image-20250927193413283](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927193413283.png)

![image-20250927193523601](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250927193523601.png)

心得：这是Java 序列化二进制文件，不是文本文件，所以会出现乱码，我再用十六进制编辑器查看试试吧。