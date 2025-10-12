## Task1.maven

##### 1.什么是maven？

Maven 是一个 Java 项目的构建和依赖管理工具，能自动下载项目所需的库（依赖），并统一管理项目结构、编译、打包等流程。

**什么是jar包？**
 JAR（Java Archive）包是 Java 程序的压缩文件，包含类文件、资源文件等，用于封装和分发 Java 库或程序。

**Maven 和 jar包有关系吗？有什么关系？**
 有关系。Maven 通过坐标（groupId、artifactId、version）从远程仓库下载所需的 jar 包，并将它们加入项目中，实现依赖管理。

**我们为什么要用 Maven？**
 因为 Maven 能简化项目构建、自动管理依赖、统一项目结构，提高开发效率，避免手动管理 jar 包带来的混乱。

**2.下载maven，安装配置成功**

![image-20251008163939645](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251008163939645.png)

Maven 仓库是存放项目依赖（如 jar 包）的地方，分为本地、远程和中央仓库。

1.怎么配置你自己的本地仓库位置？![image-20251008161528025](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251008161528025.png)

2.需要的jar包本地仓库没有？让我们去看看远程仓库！

![image-20251008184721677](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251008184721677.png)添加了阿里云镜像![image-20251012203009755](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012203009755.png)![image-20251012203024944](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012203024944.png)

3.远程仓库不止一种！你知道中央仓库是什么吗？

是 Maven 官方提供的公共仓库，地址为：`https://repo.maven.apache.org/maven2/`，包含大量常用 jar 包。

4.私服又是什么？

是公司或团队自建的私有仓库，用于存储内部 jar 包或代理中央仓库，提高下载速度和安全性。常见工具：Nexus、Artifactory。

### 4.创建你自己的maven项目！

1.你的IDEA关联maven了吗？已关联![image-20251008192739269](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251008192739269.png)![image-20251012202608017](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012202608017.png)

2.一个maven项目都需要配置什么参数？你能说说看吗？

Maven 项目需要以下关键配置：

| 参数         | 说明                                          |
| ------------ | --------------------------------------------- |
| groupId      | 组织或公司标识（如 com.example）              |
| artifactId   | 项目名称（如 myapp）                          |
| version      | 版本号（如 1.0.0）                            |
| packaging    | 打包类型（jar, war, pom）                     |
| dependencies | 依赖的第三方库（jar 包）                      |
| build        | 编译、打包等构建配置（如 source/target 版本） |

这些都在 pom.xml 文件中定义。

3.你的项目结构是什么样的？你知道你的代码、配置文件、测试代码、测试配置文件、maven项目配置文件都在哪里吗？

我的项目结构是Maven结构![image-20251008193809893](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251008193809893.png)

| 类型                   | 路径                | 示例                                                |
| ---------------------- | ------------------- | --------------------------------------------------- |
| **主程序代码**         | src/main/java/      | HelloWorld.java                                     |
| **主程序配置文件**     | src/main/resources/ | config.properties`, `database.xml                   |
| **测试代码**           | src/test/java/      | HelloWorldTest.java                                 |
| **测试配置文件**       | src/test/resources/ | test-config.properties                              |
| **Maven 项目配置文件** | pom.xml             | 在我的项目根目录下D:\steam3\JavaProjects\HelloWorld |

4.pom.xml文件？

**这是什么？**

pom.xml 是 Project Object Model（项目对象模型） 的配置文件，是 Maven 项目的“核心”。

它就像项目的“说明书”，告诉 Maven：项目是谁的、用哪个版本、要用哪些依赖、怎么编译和打包、

**它有什么用？**

   管理依赖：自动下载 jar 包（比如 Spring、Apache Commons）

   统一构建流程：compile, test, package, install

   版本控制：管理项目版本和依赖版本

   多模块支持：大型项目可以拆成多个子项目

   插件集成：如编译、打包、部署工具

**它的基本配置有哪些？**

它的基本配置是：![image-20251008194510776](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251008194510776.png)

![image-20251008194527472](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251008194527472.png)**你能通过这个文件管理你的jar包版本、项目类型吗？**

可以

管理 jar 包版本：在 <dependencies>中指定 version

管理项目类型：通过 packaging设置为 jar, war, 或 pom

统一版本管理：可以用 <properties>定义版本别名，避免重复

![image-20251012202659399](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012202659399.png)![image-20251012202713347](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012202713347.png)![image-20251012202723183](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012202723183.png)

**怎么导入你需要的jar包？去找到答案吧！**

### 5.启动你的maven！

1.maven的常用命令有哪些你知道吗？

- mvn clean：清除编译产物
- mvn compile：编译源码
- mvn test：运行测试
- mvn package：打包（生成 jar/war）
- mvn install：安装到本地仓库
- mvn deploy：部署到远程仓库

2.图形化界面是非常方便的，去观察IDEA中的maven面板，看看可以快速执行哪些maven指令吧！![image-20251012202437365](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012202437365.png)

## Task2.快递取件码查询系统

李华成功通过高考考进了UESTC，开学第一天他发现他的宿舍在校外，如果要拿快递的话要去到校内的菜鸟驿站，比较远。所以他决定手搓一个快递柜，请你帮他编写一个客户端和服务端的程序，实现通过快递单号查询取件码的功能。

### 知识准备

**maven**

**HTTP（HyperText Transfer Protocol）**：应用层协议，用于客户端（浏览器/APP）与服务端之间的数据传输。

特点

- 无状态（每个请求独立，默认不记录历史）
- 基于请求-响应模型
- 支持明文（HTTP）和加密（HTTPS）传输

请求报文样例

需要了解常见的请求方式，以及常见的响应状态码（404 应该是最熟悉的状态码了）

### 项目实现

服务端

![image-20251011140340962](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251011140340962.png)

![image-20251011140356668](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251011140356668.png)

![image-20251011140405886](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251011140405886.png)

![image-20251011140414728](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251011140414728.png)

客户端![image-20251012200157865](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012200157865.png)![image-20251012200209912](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012200209912.png)

![image-20251012200219688](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012200219688.png)

User![image-20251012200958256](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012200958256.png)

另一种方式：创建ExpressRequest.java![image-20251012200919973](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012200919973.png)

![image-20251012200932866](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012200932866.png)

![image-20251012200943456](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012200943456.png)



![image-20251012201011029](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251012201011029.png)