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
### 一些常用命令
* git status: 确定文件当前所处Git工作区域
1. 工作区文件转入暂存区 <br>
```
git status
git add HelloWorld.cpp；
```
2. 暂存区转入Git仓库 <br>
```
git status
git commit –m '提交描述'
```
3. 删除工作区文件 <br>
```
git rm -f 文件名
```
4. 修改文件 <br>
```
vi 文件名
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




