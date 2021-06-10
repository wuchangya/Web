# Git概述

Git是一个免费的、开源的**==分布式版本控制系统==**，可以快速高效地处理从小型到大型的各种项目。

Gt易于学习，占地面积小，性能极快。它具有廉价的本地库，方便的暂存区域和多个工作流分支等特性。其性能优于 Subversion、CVS、 Perforce和ClearCase等版本控制工具。

## 版本控制工具

**==集中式版本控制工具==**

CVS、SVN( Subversion)、VSS

集中化的版本控制系统诸如CVS、SWN等，都有一个单一的集中管理的服务器，保存所有文件的修订版本，而协同工作的人们都通过客户端连到这台服务器，取出最新的文件或者提交更新。

多年以来，这已成为版本控制系统的标准做法这种做法带来了许多好处，每个人都可以在一定程度上看到项目中的其他人正在做些什么。而管理员也可以轻松掌控每个开发者的权限，并且管理一个集中化的版本控制系统，要远比在各个客户端上维护本地数据库来得轻松容易

事分两面，有好有坏。这么做显而易见的缺点是中央服务器的单点故障。如果服务器宕机一小时，那么在这一小时内，谁都无法提交更新，也就无法协同工作。



**==分布式版本控制工具==**

Git、 Mercurial、 Bazaar、 Darcs

像Git这种分布式版本控制工具，客户端提取的不是最新版本的文件快照，而是把代码仓库完整地镜像下来（本地库）。这样任何一处协同工作用的文件发生故障，事后都可以用其他客户端的本地仓库进行恢复。因为每个客户端的每一次文件提取操作，实际上都是一次对整个文件仓库的完整备份。

分布式的版本控制系统出现之后，解决了集中式版本控制系统的缺陷：

1.服务器断网的情况下也可以进行开发（因为版本控制是在本地进行的）

2.每个客户端保存的也都是整个完整的项目(包含历史记录，更加安全)





## Git工作机制



![1619486512132](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1619486512132.png)





## Git和代码托管中心

代码托管中心是基于网络服务器的远程代码仓库，一般我们简单称为**==远程库==**。

局域网： Gitlab

互联网：Github（外网）、Gitee 1码云（国内网站）



#  git常用命令

![image-20210427141213045](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427141213045.png)

## 设置用户签名和邮箱

签名的作用是区分不同操作者身份。用户的签名信息在每一个版本的提交信息中能够看到，以此确认本次提交是谁做的。Git首次安装必须设置一下用户签名，**==否则无法提交代码==**。

**==※注意：这里设置用户签名和将来登录 Github（或其他代码托管中心）的账号没有任何关系==**



## 初始化本地库

在**==自己项目的根目录下==**进行初始化git，才能使用git管理这个项目



新建一个目录

git init初始化本地库，初始化后会生成一个.git 文件，一般这个文件是隐藏的

查看本地库状态

![image-20210427144256699](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427144256699.png)

在工作目录下创建一个文件

然后再次查看本地库状态

![image-20210427144441701](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427144441701.png)



## 添加暂存区

使用git add  文件名 ，来跟踪文件，即将文件添加到暂存区

![image-20210427144642290](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427144642290.png)

这里有一个提示：将换行符从==CRLF==(windows中的换行符)改成==LF==(Linux中的换行符)

（安装git的过程时自己已经选择了允许自动转换行目换行符）

再次查看本地库的状态

![image-20210427145409975](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427145409975.png)

提示可以使用 git rm-- cached文件名来将暂存区的文件删除，取消跟踪的状态，但并末删除磁盘空间里的文件，在工作区的文件夹中仍能找到



## 提交本地库

**==git commit -m "版本/日志信息" 文件名==**

-m后面紧跟着的是版本/日志信息

![image-20210427150636241](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427150636241.png)



再次查看本地库的状态

![image-20210427150736411](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427150736411.png)

查看版本信息记录

![image-20210427150939772](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427150939772.png)

查看详细的日志信息

![image-20210427151216926](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427151216926.png)



## 修改文件

打开工作目录下的hello.txt 文件进行修改

修改过后再次查看本地库的状态

![image-20210427151427005](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427151427005.png)

提示文件已经被修改，并且没有进行追踪，没有添加到暂存区

需要再次将hello.txt 文件添加到暂存区

![image-20210427152350865](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427152350865.png)

然后再次提交至本地库，这时候的版本信息可以写second commit

![image-20210427152609925](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427152609925.png)

（如果我们修改了一行，这时候会显示1 insertion(+), 1 deletion(-)，因为git是按行来维护文件的，修改了一行，相当于新增一行，然后再删除旧的那行）

查看版本信息，发现已经有两个版本了

![image-20210427152859435](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427152859435.png)



## 版本穿梭

在当前的git下查看文件内容，默认的是最新版本，并且只能查看这一个版本的文件内容，如下

![image-20210427153358766](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427153358766.png)

如果想查看之前版本的文件，使用版本穿梭： **==git reset --hard 想要穿梭到的版本号==**

![image-20210427155221261](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427155221261.png)

这样就将当前的版本改成了指定的版本，查看的文件也是此版本的文件

![image-20210427155307974](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427155307974.png)

查看当前的状态

![image-20210427155427223](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427155427223.png)

每次查看状态其实都会有蓝色的一个指针，这个代表当前指向的版本

**==此时本地工作空间（即本地的磁盘空间中）中相应的文件也发生了改变，变成了指定版本的内容==**

在创建多个版本的时候，git在本地的内存中记录了很多的日志与版本信息，通过调用指针来指向不同的版本，明面上只有一个版本



# git的分支操作

## 分支介绍

什么是分支

在版本控制过程中，同时推进多个任务，为每个任务，我们就可以创建每个任务的单独分支。

使用分支意味着程序员可以把自己的工作从开发主线上分离开来，开发自己分支的时候，不会影响主线分支的运行。

对于初学者而言，**==分支可以简单地理解为副本==**，一个分支就是一个单独的副本。（分支底层其实也是指针的引用）

![image-20210427160242654](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427160242654.png)

**==举个例子==**：上面这个图中，对于服务器，程序员肯定不能指直接在用户使用着的服务器上进行开发，所以服务器至少两个分支一个线上分支（master），一个生产分支（dev）

![image-20210427161040172](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427161040172.png)

同时并行推进多个功能开发，操高开发效率。各个分支在开发过程中，如果某一个分支开发失败，不会对其他分支有任何影响。失败
的分支删除重新开始即可。



## 分支的操作

![image-20210427161202607](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427161202607.png)



### 查看分支

git branch -v 分支名

查看当前工作目录下有几个分支

![image-20210427161434480](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427161434480.png)

### 创建分支

git branch 分支名

创建一个分支

![image-20210427161627556](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427161627556.png)

### 切换分支

git checkout 分支名

切换分支

![image-20210427161826689](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427161826689.png)

然后就可以在当前的分支下进行修改、追踪、提交

打开工作目录的文件，打开的也是这个分支下的文件



### 合并分支

git merge 分支名 

**==把指定的分支合并到当前的分支上==**

在hot-fix分支中的hello.txt文件中进行修改，然后回到master分支中，将hot-fix分支合并到master分支中

![image-20210427172549261](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427172549261.png)

master中的hello.txt 文件变成了hto-fix中修改后的样子

这样的修改属于无冲突合并



#### 合并分支产生冲突

**==冲突产生的原因：==**

合并分支时，两个分支在**同一个文件的同一个位置**有两套完全不同的修改。Git无法替我们决定使用哪一个。

必须**人为决定**新代码内容

例子：

在master分支中的hello.txt修改最后一行，加上master test

![image-20210427173756540](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427173756540.png) 

然后追踪、提交

然后切换到hot-fix分支下，同样修改hello.txt 文件，在最后一行加上hot-fix test

![image-20210427174053507](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427174053507.png)

然后追踪、提交

这时候回到master分支中将hot-fix分支合并到master分支中

这时候会报错

![image-20210427174435474](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427174435474.png)

这时候需要手动打开文件进行合并

打开hello.txt 文件

![image-20210427174729042](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427174729042.png)

手动进行删除，就比如两个分支的内容都想要，如下图

![image-20210427174814212](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427174814212.png)

修改好后然后再进行追踪、提交

但是这个时候提交会报一个错误，如下

![image-20210427175427596](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427175427596.png)

**==所以，人为合并分支后，在进行到提交这一步时，提交最后不要写文件名就可以了==**

![image-20210427175632540](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427175632540.png)



# git团队合作机制

上面讲到的都是在本地进行操作

以后的团队合作需要一个**==代码托管中心==**，需要将代码推送到代码托管中心，然后大家就可以都能拿到这个代码了



团队协作机制有两种：**==团队内协作、跨团队协作==**

## 团队内协作

![image-20210427180234415](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427180234415.png)



## 跨团队协作

![image-20210427180504457](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427180504457.png)



# github

## 远程仓库操作

![image-20210427191820804](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427191820804.png)

### 创建远程仓库别名

创建远程仓库的别名

**==git remote add 别名 远程地址==**

![image-20210427192206484](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427192206484.png)

然后查看当前所有远程地址的别名



==**git remote remove 别名**== ：即可删除这个别名对应的远程仓库信息！

**==git remote -v==** 

![image-20210427192432848](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427192432848.png)

会查询到有两个别名，是同一个仓库的拉取和推送别名



### 推送本地库到远程库

**==git push 别名/仓库地址 分支名==**

中途会有登录的过程

登录上后就会出现如下的成功提示

![image-20210427195003015](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427195003015.png)



然后刷新仓库，仓库中就会有相应本地库的代码

![image-20210427195139823](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427195139823.png)



### 拉取远程库到本地库

**==git pull 别名/仓库地址 分支名==**

![image-20210427195623292](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427195623292.png)

==**拉取后，在本地库的分支中git自动帮我们进行追踪、提交**==，**==本地库的代码跟远程库的代码进行同步了==**



### 克隆远程库到本地

在想要克隆的文件夹中打开git bash

**==git clone 远程地址==**

![image-20210427200746626](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427200746626.png)

![image-20210427200801497](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427200801497.png)

==**git克隆命令其实做了三件事情：**==

==**1.拉取代码**==

==**2.初始化本地仓库**==

==**3.创建别名**==

别名可以使用git remote -v来查看

![image-20210427201049980](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427201049980.png)

将我们这个克隆的远程地址默认取origin的别名





## 团队内协作

**==要想往远程库里面推送代码，需要加入到团队才可以==**

要想允许别人往自己的仓库里面进行pull操作

需要在自己仓库的setting中进行设置，来邀请别人

![image-20210427202530554](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427202530554.png)

然后搜索，邀请

![image-20210427202632941](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427202632941.png)

然后页面下面就会出现一个**==邀请函==**，复制邀请函，邀请函其实也是一个链接

![image-20210427202646526](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427202646526.png)

将这个邀请函发给要加入的那个人

领一个人打开链接，然后接收邀请，之后就可以进行**==push==**操作了

![image-20210427202843802](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427202843802.png)

## 跨团队协作

首先，在git左上角可以搜索项目

如果团队外的成员想要搜索某一项目，为避免搜索结果的项目太多了，**==在项目前面加上项目的用户名==**，可快速搜索项目

当然也可以直接使用**==项目的链接==**



打开这个项目后，如果想协助完成这个项目，点击项目右上角的**==fork==**（叉子，相当于以一个团队外的身份将这个项目插到自己的账号中去）

![image-20210427203735657](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427203735657.png)



然后打开自己的主页，在左边就发现有了这个项目

![image-20210427204011072](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427204011072.png)

这里作为例子，直接在网页里进行修改，修改后，点击**==Pull request==**，发送拉取请求，发送给项目的拥有者

![image-20210427204237223](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427204237223.png)

再点击New pull requset

![image-20210427204425591](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427204425591.png)

点击之后，再点击**==Create pull request==**

![image-20210427204526816](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427204526816.png)

然后可以对项目进行一些描述和 通知写在下面 ，完成之后点击**==Create pull request==**

![image-20210427204727072](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427204727072.png)

项目的原本的拥有者的项目中，就看到了拉取请求

![image-20210427204915956](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427204915956.png)

打开拉取请求后，可以查看项目内容，也可以双发进行留言聊天，如果审核没问题后，就点击下面的**==merge pull request==**，进行最后的合并

![image-20210427205027794](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427205027794.png)



## SSH免密登录

在我们赋值代码链接的时候，**==默认选择的是https的链接==**

除了这个还有一个**==SSH链接==**

![image-20210427205453084](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427205453084.png)

但这个时候我们用不了SSH的链接



打开自己**==c盘的用户文件夹==**

![image-20210427205659202](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427205659202.png)

右键打开git bash

输入命令**==ssh-keygen -t rsa -C 用户邮箱==**

-t后面是用来指定加密协议，这里用的是rsa

-C 后面跟的是要绑定的用户邮箱

然后剩下的参数设置直接点击三次回车

![image-20210427210257008](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427210257008.png)

之后用户文件夹中就有了.ssh文件夹

![image-20210427210352514](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427210352514.png)

打开里面有两个秘钥文件，一个公钥，一个私钥

![image-20210427210452487](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427210452487.png)

进入到这个.ssh文件中，拿到文件中的公钥，复制下来

![image-20210427210725497](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427210725497.png) 

再打开git自己用用户设置settings的界面，打开SSH and GPG keys设置界面，进行公钥的添加

![image-20210427210947934](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427210947934.png)



为公钥取一个名字，然后将公钥复制进来

![image-20210427211140738](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427211140738.png)

添加成功

![image-20210427211301852](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427211301852.png)



然后就可以用**==ssh免密登录==**来上传代码了了，**==push的时候直接用ssh的链接，并不用登录了==**

![image-20210427211453939](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210427211453939.png)







# GitLab

## 简介和环境准备

GitLab 是由 GitLabInc.开发，使用 MIT 许可证的基于网络的 Git 仓库管理工具，且具有 wiki 和 issue 跟踪功能。使用 Git 作为代码管理工具，并在此基础上搭建起来的 web 服务。 GitLab 由乌克兰程序员 DmitriyZaporozhets 和 ValerySizov 开发，它使用 Ruby 语言写 成。后来，一些部分用 Go 语言重写。截止 2018 年 5 月，该公司约有 290 名团队成员，以 及 2000 多名开源贡献者。GitLab 被 IBM，Sony，JülichResearchCenter，NASA，Alibaba， Invincea，O’ReillyMedia，Leibniz-Rechenzentrum(LRZ)，CERN，SpaceX 等组织使用。





















































































































































































































































































































# ps:

## 在vim中复制操作：

在vim中，点i进行输入

按esc，然后光标放在想要复制的那一行，按yy进行复制，按p进行粘贴



## 在git bash中复制粘贴快捷键

ctrl + Fn + Ins(Del)：复制

shift + Fn + Ins(Del)：粘贴





















































