## **backend-plus-02**

#### **Task.01 Git——不仅仅是commit**

当你执行git init或者git clone时，你是否注意到工作区出现的.git文件？你知道它是什么吗？里面都放了什么？

**1.git的分支是什么？如何创建/切换/合并分支？merge和rebase的区别是什么？**

- **分支**：就像一条条并行的“小路”，你可以在一个分支上改代码，不影响主路（main）。

- **创建分支**：`git branch feature-login`

- **切换分支**：`git checkout feature-login` 或 `git switch feature-login`

- 合并分支：

  merge：把两个分支的内容“拼”在一起，会生成一个“合并提交”。

  rebase：把你的修改“搬”到另一个分支后面，看起来像是一直在一条线上改，更干净。

merge是“合并”，rebase 是“重放”。

**2.HEAD是什么，它有哪些状态，相对引用如何使用？**

- **HEAD**：就是你当前所在的“位置”，比如你现在在哪个分支。

- 它的状态有三种：

  指向某个提交（commit）

  指向某个分支名（比如 main）

  指向一个标签（tag）

- 相对引用：

  HEAD~1：上一个提交

  HEAD~2：上上个提交

  HEAD^：同 HEAD~1

 用来快速定位历史版本。

**3.什么是远程分支？你知道main与origin/main的关系吗？**

- 远程分支：别人仓库里的分支，比如 GitHub 上的 main。

- origin/main：是本地对远程main的“影子”。

  main：本地的主分支

  origin/main：从远程拉下来的主分支

 每次 pull 就是把 origin/main 同步到你的 main。

**4.什么是git冲突？如何解决？**

- **冲突**：两个人改了同一段代码，Git 不知道该保留谁的。
- 解决方法：
  1. 手动打开冲突文件，看到 <<<<<<<, =======, >>>>>>> 标记
  2. 选择保留哪部分代码
  3. 删除标记，保存文件
  4. git add 文件名→ git commit

**5.fetch和pull有什么区别？**

- git fetch：只下载别人改了什么，不自动合并，安全。
- git pull：等于 fetch + merge，直接把别人的东西合并进来。

推荐先 fetch 看看变化，再决定要不要 merge。

**6.什么是锁定的main分支？什么是PR？为什么要这么做？有什么好处？**

- **锁定 main 分支**：不允许直接 push 到 main，防止误操作。

- **PR（Pull Request）**：提一个申请，让别人审核你的代码再合并。

- 为什么要这样做？

  防止乱改代码

  让团队一起检查质量

  更安全、更规范

 好处：代码更稳定，协作更清晰。

**7.简单了解一下git flow工作流**

git flow是一种标准开发流程：

1. 从 develop分支开发新功能
2. 功能做好后，合并到 develop
3. 准备发布时，从 develop创建 release 分支
4. 发布后，合并到 main 和 develop
5. 修复 bug 用 hotfix 分支

结构清晰，适合团队项目。

总结：Git 不只是“add、commit、push”，它是团队协作的“交通规则”和“版本记录本”。掌握这些，就能高效又安全地写代码啦。

#### **模拟场景01**

1.先制造一个“误提交敏感文件”的错误场景![image-20251015103244360](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015103244360.png)

尝试修复——添加 .gitignore——更新 .gitignore——提交这个更改——模拟 push 到远程仓库（ GitHub）被拒

![](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015104408959.png)

为什么第二次push还报错？

**因为：**

- 第一次 commit 时，提交了密钥文件 → 它已经进入 Git 的历史
- 虽然现在修改了 .gitignore并重新 commit，但 Git 不会自动删除已提交的文件
- 所以当 push时，系统仍然会检查所有提交，发现有敏感文件 → 报错！

![image-20251015110526241](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015110526241.png)

**正确解决方法：从 Git 历史中删除该文件**

**步骤一**：进入该文件 id_rsa

**步骤二：**使用 git filter-repo删除文件

1.先安装，pip install git-filter-repo；![image-20251015112242377](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015112242377.png)2.再删除特定文件id_rsa：git filter-repo --path . --exclude "id_rsa"；![image-20251015112726169](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015112726169.png)3.更新 .gitignore，最后推送新历史到远程：git push origin master --force-with-lease![image-20251015113300127](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015113300127.png)

**步骤四：**再次 push：重新添加远程仓库（origin）——确保 .gitignore忽略敏感文件——强制推送新历史到远程

![image-20251015113602451](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015113602451.png)

心得经验：不要直接删掉 .gitignore中的文件就 push， 不要以为改了 .gitignore就能“擦除”历史。Git 是版本控制系统，一旦提交，就不能“假装没发生”。必须主动清理历史。



#### **模拟场景02**

创建测试项目——创建 main 和 develop 分支——模拟微光娘在 develop 上开发登录功能，包括“未提交的更改”场景

![image-20251015114521854](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015114521854.png)

![image-20251015114541806](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015114541806.png)

![image-20251015114951877](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015114951877.png)

##### 目标

1. 把她在 develop 上的修改合法化
2. 不破坏团队协作流程
3. 最终让她的代码合并进 develop，并删除她乱改的分支



**为什么不能直接删掉 develop？**

因为她已经把代码推到了 develop，如果直接删，会导致：

其他人无法拉取最新代码

可能造成数据丢失或混乱

所以我们要保留她的修改，只是换一种合规的方式让它进入主干。



**解决方法**

创建新的 feature 分支（用于修复）![image-20251015201936265](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015201936265.png)

重置 develop 分支（回到干净状态）![image-20251015201947903](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015201947903.png)找到那个提交的哈希![image-20251015202107783](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015202107783.png)

将 login.js 的改动移到 feature/login-fix分支![image-20251015202416301](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015202416301.png)

步骤四：清理本地 develop 分支![image-20251015202658450](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015202658450.png)

步骤五：推送 feature 分支并申请 PR![image-20251015202740914](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015202740914.png)

步骤六：审核后合并到 develop

![image-20251015203015465](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20251015203015465.png)