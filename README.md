# Git 笔记 

## 创建版本库 

版本库又名仓库(repository)，可以简单的理解成为一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻“还原”。  

选择一个合适的地方创建一个空目录：  

'''
mkdir learn_git
cd learn_git

git init # 初始化git仓库

# 添加文件

git add [文件名] # 把文件添加到仓库。 `.`添加全部文件到仓库
git commit -m "wrote a README.md" # 把文件提交到仓库。`-m`后是本次提交的说明

'''  


