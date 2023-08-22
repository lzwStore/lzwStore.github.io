---
title: git
date: 2023-06-21 15:38:45
categories: [前端, git]
tags: git
cover: /img/git/git.jpg
---

## git 基本命令

```bash
git init # 初始化 git 仓库

git add . # 添加到暂存区

git commit -m '提交信息' # 把本次提交内容添加到本地仓库

git push # 推送到远程 如果没有绑定远程分支 会出现提示的命令 复制提示的命令重新执行即可

git branch --set-upstream-to=origin/远程分支名称  # 推送到远程指定分支

git pull # 拉取远程分支代码 如果没有绑定会提示 按提示操作

git checkout 'develop' # 切换到 develop 分支

git checkout -b 'develop' # 创建并切换到 develop 分支

git branch # 查看本地所有分支

git branch -D 'develop' # 强制删除本地 develop 分支

```

## git 关闭忽略文件大小写
```bash
git config core.ignorecase false
```

## 强大的 git stash
```bash
# 储藏工作区的所有内容
git stash 

# 储藏工作区内容并且添加备注
git stash save '备注备注'

# 查看储藏区的所有文件
git stash list

# 取出储藏区的第一个文件
git stash pop

# 取出指定储藏区的的文件 stash@{index} 对应索引
git stash apply stash@{index}

# 例: 取出stash list 中的第一项
git stash apply 1

# 将指定index的储藏从储藏记录列表中删除 stash@{index}
git stash drop stash@{index}

# 清空储藏区
git stash clear
```

## git版本回退

```bash
# 回退到上一次commit之前的内容 对之前代码做的改动都还在 好用
git reset HEAD^

# 回退到某个版本 改变的差异在工作区　对代码做的改动都还在 好用
git reset 057ddfe    ||   git reset --mixed 057ddfe

# 回退到某个版本 回退的版本和现在版本的差异出现在暂存区 对代码做的改动都还在 好用
git reset --soft b7de7a23fa3

# 回退到某个版本 并且把之前commit的内容全部清空掉  不可逆! 慎用!!!
git reset --hard b7de7a23fa3　

# 撤回上次 git reset HEAD^ 的内容
git reset ORIG_HEAD

```

# git cherry-pick

```bash
# 把某次提交的内容提取到当前分支
git cherry-pick commitId

```


