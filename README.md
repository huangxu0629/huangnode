# huangnode
# 1.  使用Github　　
## 1.1 目的
借助github托管项目代码
## 1.2 基本概念
### 仓库（Repository）
每个项目对应一个仓库，仓库用来存放项目的代码
### 收藏（star）
收藏项目的人数，方便下次查看
### 复制克隆项目（Fork）
复制一份别人的仓库 `是独立存在的`
### 发起请求（Poll Request）
在`Fork`的基础上，发起合并请求，把修改合并到原项目上
### 关注（watch）
# 2.创建仓库
一个git库（仓库）对应一个开源项目<br>
通过`git`管理仓库
# 3. issues
对项目提出问题，与项目发布者进行交流
# 4. Git安装和使用
## 4.1 目的
Git全称是分布式版本控制系统，可以有效、高速的处理从很小到非常大的项目版本管理(通过`git`管理`github`托管项目的代码 )。每个开发者可以通过克隆`git clone`，在本地机器上拷贝一个完整的Git仓库 <br>
官方下载地址：(https://git-scm.com/download/win)  
## 4.2 Git基本工作流程
### Git工作区域
![Git三大分区](https://img-blog.csdnimg.cn/20200830233909569.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
1. 工作区（Working Directory） <br>
添加、编辑、修改文件
2. 暂存区 <br>
 暂存已经修改的文件最后统一提交到Git仓库中
3. Git仓库（Git Repository） <br>
最终确定的文件保存到仓库，成为一个新的版本，并对他人可见
### 初始化本地仓库
1. 创建文件夹 <br>
2. 在文件夹内初始化Git（创建Git 仓库）<br>
命令行进入当前目录，使用`git init`命令，在你的项目根目录中新建了一个隐藏文件夹（.git）
### 本地的代码如何提交到远程仓库中
* git status: 确定文件当前所处Git工作区域
1. 工作区文件转入暂存区 <br>
```
git status
git add HelloWorld.cpp；
git add .  (将文件夹中所有文件添加到本地仓库)
```
2. 暂存区转入Git仓库（**本地仓库**） <br>
```
git status
git commit –m '提交描述'
```
此命令会将git add .存入暂存区的修改文件提交至本地仓库中，若文件未添加至暂存区，则提交时不会提交任何修改。 <br>
3. 建立本地仓库和github**远程仓库**的关联 <br>
```
git remote add origin https://github.com/*****/*****.git   
origin后面跟你的github仓库地址(ssh地址)
```
3. Git仓库同步到Github**远程仓库** <br>
```
git push <远程地址> <本地分支名><:><远程分支名>
git push -u origin master （第一次使用加上了-u参数，是推送内容并关联分支）
推送成功后就可以看到远程和本地的内容一模一样，下次只要本地作了提交，就可以通过命令：
git push origin master
把最新内容推送到Github上的上
```
上面命令表示，将本地的master分支推送到origin主机的master分支。如果master不存在，则会被新建
### 远程仓库（Github对应的项目）复制到本地仓库
```
git clone 仓库地址(仓库地址在clone or download按钮下取得)
```
### 一些常见命令
1. 删除工作区文件 <br>
```
git rm -f 文件名
```
2. 修改文件 <br>
```
vi 文件名
```
### 本地如何进行分支管理
1. 查看本地有哪些分支
```
git branch
```
2. 切换分支
```
git checkout 分支名
```
3. 新建分支
```
git branch 分支名
```
### Git基本设置
1. 设置用户名 <br>
```
git config --global user.name '用户名'
```
2. 设置用户邮箱 <br>
```
git config --global user.email '邮箱名'
```
### Github配置SSH Key
```
https://github.com/xiangshuo1992/preload.git
git@github.com:xiangshuo1992/preload.git
```
这两个地址展示的是同一个项目，但是这两个地址之间有什么联系呢？
  前者是https url 直接有效网址打开，但是用户每次通过git提交的时候都要输入用户名和密码，有没有简单的一点的办法，一次配置，永久使用呢？当然，所以有了第二种地址，也就是SSH URL，那如何配置就是本文要分享的内容。
  
GitHub配置SSH Key的目的是为了帮助我们在通过git提交代码是，不需要繁琐的验证过程，简化操作流程。 <br>
1. 设置git的user name和email <br>
如果你是第一次使用，或者还没有配置过的话需要操作一下命令，自行替换相应字段。
```
git config --global user.name "Luke.Deng"
git config --global user.email  "xiangshuo1992@gmail.com"
```
`git config --list` 查看当前Git环境所有配置，还可以配置一些命令别名之类的 <br>
  2. 检查是否存在SSH Key
```
cd ~/.ssh
ls
或者
ll
//看是否存在 id_rsa 和 id_rsa.pub文件，如果存在，说明已经有SSH Key
```
3. 如果没有SSH Key，则需要先生成一下
```
ssh-keygen -t rsa -C "xiangshuo1992@gmail.com"
```
![图片](https://exp-picture.cdn.bcebos.com/38332303bbea3e8680bc70f75cd4483105eb5548.jpg?x-bce-process=image%2Fresize%2Cm_lfit%2Cw_500%2Climit_1) <br>
   当我们创建好ssh key的时候，我们到我们的用户主目录会发现一个.ssh目录，然后在目录里会有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人 <br>
4. 获取SSH Key
```
cat ~/.ssh/id_rsa.pub
或者
cat id_rsa.pub
//拷贝秘钥 ssh-rsa开头
```
5. GitHub添加SSH Key <br>
```
首先在个人中心点击settings进入到个人界面下拉选择SSH and GPG keys在右上角有个叫New SSH keys（新的密钥）点击进去添加SSH密钥
```
6. 测试是否成功配置SSH Key
```
ssh -T git@github.com
//运行结果出现类似如下
Hi xiangshuo1992! You've successfully authenticated, but GitHub does not provide shell access.
```
7. 之前已经是https的链接，现在想要用SSH提交怎么办？ <br>
直接修改项目目录下 .git文件夹下的config文件，将地址修改一下就好了。 <br>
git地址获取可以看如下图切换 <br>
![地址切换](https://img-blog.csdnimg.cn/20181029093141515.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTM3Nzg5MDU=,size_12,color_FFFFFF,t_70)
# 5. 搭建自己的个人博客
## jekyll的下载安装
### 安装ruby 
因为jekyll依赖于ruby，所以必须先安装ruby
[下载网址](https://www.ruby-lang.org/en/downloads/)
### 测试是否安装成功
![测试](https://img-blog.csdnimg.cn/20190228134740728.PNG)
### 安装jekyll
在命令行中输入`gem install jekyll`，jekyll安装完成后，还不能使用，还要安装一些组件。此时在命令行中输入`gem install bundler`，安装完成后，再在命令行中输入`bundle install`。这些步骤做完之后，jekyll就可以使用了
# 6. 参考资料
[如何使用GitHub创建一个自己的博客并且上传](https://blog.csdn.net/weixin_46323637/article/details/108287483) <br>
[GitHub如何配置SSH Key](https://blog.csdn.net/u013778905/article/details/83501204) <br>
[Markdown基本语法](https://www.jianshu.com/p/191d1e21f7ed/)




