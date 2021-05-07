# Git 笔记

## 远程仓库

第一步，创建SSH Key。在用户目录下看看有没有.ssh目录，如果有，再看看这个目录下有没有`id_rsa`和`id_rsa.pub`这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：

```ssh
ssh-keygen -t rsa -C "youremail@example.com"
```

一路回车，使用默认值即可，需要调整可以自行调整。

一切顺利的话，可以在用户主目录里找到`.ssh`目录，里面有`id_rsa`和`id_rsa.pub`两个文件，这两个就是SSH Key的秘钥对，`id_rsa`是私钥，不能泄露出去，`id_rsa.pub`是公钥，可以放心地告诉任何人。

第二步，登录Github，打开“Account settings” -- ”SSH and GPG keys“ -- “SSH Keys”页面：新建一个SSH Key，把`id_rsa.pub`的内容填上。

第三步，运行

```git
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

## 创建版本库

版本库又名仓库(repository)，可以简单的理解成为一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻“还原”。  

选择一个合适的地方创建一个空目录：

```git
mkdir learn_git
cd learn_git  

git init # 初始化git仓库  

# 添加文件  

git add [文件名] # 把文件添加到仓库。 `.`添加全部文件到仓库
git commit -m "wrote a README.md" # 把文件提交到仓库。`-m`后是本次提交的说明  

git branch -M master # `-M`:移动/重命名一个分支，即使目标已存在
git remote add origin git@github.com:xxx/learn_git.git # 关联远程仓库
git push -u origin master # 把本地内容推送到远程仓库上。 `-u`:设置 git pull/status 的上游
# 之后用`git push origin master`推送即可  
```
