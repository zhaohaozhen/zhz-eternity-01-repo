## **backend-plus-01 **

#### **Task.02 熟悉Linux**

1.**了解 Linux 目录结构**

Linux 的目录结构是树状的，根目录是 `/`。

常见目录说明：

| 目录    | 用途                                          |
| ------- | --------------------------------------------- |
| `/bin`  | 常用命令（如 ls, cp, mv）                     |
| `/etc`  | 配置文件（如 nginx.conf、docker-compose.yml） |
| `/home` | 用户家目录（如 `/home/user`）                 |
| `/var`  | 可变数据（日志、缓存等）                      |
| `/tmp`  | 临时文件                                      |
| `/usr`  | 用户程序和库                                  |
| `/opt`  | 第三方软件安装目录                            |

2.**熟悉常用 Linux 命令**

| 命令                      | 作用                   |
| ------------------------- | ---------------------- |
| `ls`                      | 列出文件               |
| `ls -l`                   | 详细列表               |
| `ls -la`                  | 包括隐藏文件           |
| `cd`                      | 切换目录               |
| `cd ..`                   | 回到上级目录           |
| `cd ~`                    | 回到家目录             |
| `pwd`                     | 显示当前路径           |
| `mkdir dir_name`          | 创建目录               |
| `rm file.txt`             | 删除文件               |
| `rm -rf dir_name`         | 强制删除目录（谨慎！） |
| `cp file1 file2`          | 复制文件               |
| `mv file1 file2`          | 移动/重命名文件        |
| `touch file.txt`          | 创建空文件             |
| `cat file.txt`            | 查看文件内容           |
| `grep "keyword" file.txt` | 搜索关键字             |
| `man command`             | 查看命令帮助           |

3.**掌握包管理器的使用**

| 发行版        | 包管理器       | 示例                                       |
| ------------- | -------------- | ------------------------------------------ |
| Ubuntu/Debian | `apt`          | `sudo apt update && sudo apt install curl` |
| CentOS/RHEL   | `yum` 或 `dnf` | `sudo yum install vim`                     |
| Fedora        | `dnf`          | `sudo dnf install git`                     |
| Arch Linux    | `pacman`       | `sudo pacman -S firefox`                   |

4.**配置自己喜欢的 Shell（如 zsh)**

![image-20251014175300859](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014175300859.png)

#### **Task.03 SSH远程开发**

##### 1. SSH连接

什么是 SSH 密钥？

- 一对密钥：公钥（public key）和 私钥（private key）
- 公钥放在服务器上，私钥留在本地
- 登录时用私钥“证明身份”，实现免密登录

生成了 SSH 密钥![image-20251014181822238](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014181822238.png)

将公钥添加到了 GitHub 账户，克隆了仓库![image-20251014181956875](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014181956875.png)ssh已连接![image-20251014193228610](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014193228610.png)

##### 2.用密钥实现免密码登录

![image-20251014193942385](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014193942385.png)

![image-20251014194429903](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014194429903.png)

![image-20251014194354700](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014194354700.png)

**3.进阶挑战**

生成一对新的 SSH 密钥（专门用于 GitHub）

![image-20251014194905754](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014194905754.png)

将公钥添加到 GitHub 账号

SSH 已经成功连接 GitHub![image-20251014195228993](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014195228993.png)![image-20251014195257804](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014195257804.png)

使用 `git clone git@github.com:xxx/xxx.git` 方式操作仓库

克隆了仓库

![image-20251014200143522](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014200143522.png)

远程地址![image-20251014200437820](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014200437820.png)远程地址从 HTTPS 改为 SSH

![image-20251014200728436](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014200728436.png)

config文件内容![image-20251014201300821](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251014201300821.png)

