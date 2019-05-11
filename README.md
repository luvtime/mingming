# 1902 - 大宝剑项目

# GIT

### GIT基本命令
* git init
* git add
* git commit
* git status
* git diff HEAD -- xxx.yyy
* git diff --staged
* git diff



### GIT版本
在Git中，用HEAD表示当前版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100
* git log
* git reset --hard HEAD^（工作区回退到指定版本）
* git reflog
* git checkout -- filename (让这个文件回到最近一次git commit或git add时的状态)
    注意：有--，才会复原文件，否则，checkout就是切换分支的命令
* git reset HEAD filename （撤销暂存区内容）


### GIT分支
* 默认分支master
* 创建分支
```bash
$ git branch dev
```
* 切换分支
```bash
$ git checkout dev
```
> 创建并切换分支(git checkout -b feature1)

* 查看当前分支
```bash
$ git branch
```

* 合并分支
```bash
$ git merge dev
```
> git merge命令用于合并指定分支到当前分支

* 删除分支
```bash
$ git branch -d dev
```



### 远程仓库
* 添加远程仓库
```bash
$ git remote add origin(远程仓库名) git@github.com:michaelliao/learngit.git
```

* 将本地库内容推送到远程仓库
```bash
$ git push -u origin master
```
> 由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来

* 从远程参考clone代码
```bash
$ git clone git@github.com:michaelliao/gitskills.git
```

### 其他命令
gitignore


### GITHUB SSH Key
* 1. 创建SSH Key
> 打开Shell（Windows下打开Git Bash），创建SSH Key：
```bash
$ ssh-keygen -t rsa -C "youremail@example.com"
```
> 你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。
* 2. 设定github
> 登陆GitHub，打开“Account settings”，“SSH Keys”页面：
> 然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
> 点“Add Key”，你就应该看到已经添加的Key