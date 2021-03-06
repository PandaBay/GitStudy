## Git 基础
这部分内容非常重要，理解了Git的思想和基本工作原理，用起来就会知其所以然，游刃有余。

### 直接记录快照，而非差异比较

### 近乎所有操作都是在本地执行
在 Git 中的绝大多数操作都只需要访问本地文件和资源，一般不需要来自网络上其它计算机信息。
### Git 保证完整性
Git 中所有数据在存储前都计算校验和，然后以校验和来引用。
这意味着不可能在 Git 不知情时更改任何文件内容或目录内容。这个功能构建在Git底层，是构成 Git 哲学不可或缺的部分。若你在传送过程中丢失 了信息或者损坏了文件，Git 就能发现
### Git一般 只添加数据
执行Git操作，几乎只往Git数据库中增加数据。Git 为提交更新时有可能丢失或者弄乱修改的内容，但是一旦你提交的快照到Git中，就难以再丢失数据，特别是如果你定期的推送本地仓库到其他仓库的话。
## 三种状态

Git 有三种状态，你的文件可能处于其中之一：已提交（commited）、已修改（modified）、已暂存（staged）。
已提交表示数据已经安全的保存在本地仓库中。
已修改表示修改了文件，但是没有保存到本地仓库中。
已暂存表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快快照中。


由此，引入了 Git 项目中三个工作区于的概念： Git仓库、工作目录和暂存区域。

### Git 仓库
Git 仓库目录是 Git 用来保存项目的元数据和对象数据库的地方。这是 Git 中最重要的部分，从其它计算机克隆仓库时，拷贝的就是这里的数据。

### 工作目录
工作目录，是对项目的某个版本独立提取出来的内容。这些从 Git 仓库的压缩数据库中提取出来的文件，放在磁盘上供你使用或者修改。

### 暂存区域
暂存区域是一个文件，保存了下次将提交的文件列表信息，一般在 Git 仓库目录中。


## Git 基本工作流程如下：

1. 在工作目录中修改文件；
2. 暂存文件，将文件的快照放入暂存区域中；
3. 提交更新，找到暂存区域的文件，将快照永久的存储到Git仓库目录中。

