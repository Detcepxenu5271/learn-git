# Git使用教程


## 原理
版本控制系统（version control system，VCS）
* 本地
* 集中化
* 分布式
	- 本地

Git 的文件结构
* .git 文件夹

三种状态
* 已提交 Commited
* 已修改 Modified
* 已暂存 Staged

git 安装
* [Download Git for Windows](https://git-scm.com/download/win)
* 设置用户名和邮箱（用途：记录信息）
	- `git config --global user.name "John Doe"`
	- `git config --global user.email johndoe@example.com`

## 创建或获取仓库
创建：`git init`

获取：`git clone`
* 从网络 clone
* 从本地 clone

## 记录更新
![lifecycle](img/lifecycle.png)

获取仓库状态：`git status`

跟踪和暂存文件：`git add`
* 暂存所有文件的几种方法
	- 命令行通配符`*`
	- `git add .`
	- `git add -A`，注意大写

忽略文件
* .gitignore

提交
* `git commit`
* `git commit -m "Commit Message"`
* `git commit --amend`

撤销修改
* `git restore --staged`
* `git restore`

## 远程仓库
查看远程仓库列表：`git remote -v`

添加远程仓库：`git remote <shortname> <url>`

从远程仓库抓取
* `git fetch <remote>`
* `git pull <remote> <branch>[:<remote_branch>]`，涉及合并操作，之后讲

推送到远程仓库
* `git push <remote> <branch>[:<remote_branch>]`

## 分支
查看分支：`git branch -vv`（两个 v 信息更多，包括远程分支的信息）

新建分支
* `git branch <branch>`
	- 删除：加`-d`
* `git checkout -b <branch>`

切换分支
* `git switch <branch>`
* `git checkout <branch>`

合并分支
* 把分支合并到当前分支（HEAD 所指）
* 类型
	- 快进（fast-forward）
		+ 应该将新的提交合并到旧的（HEAD 在旧的，merge 新的）
	- 分叉且无冲突
	- 分叉且有冲突
* 命令
	- `git merge <branch> [<branch> ...]`

回滚版本
* `git reset --hard "HEAD^"`

远程分支
* 命名：类似`origin/main`
* 跟踪：对应的本地分支，建议同名（会自动跟踪）
* 工作方法：先拉取到本地，本地合并（解决冲突）后推送上去
	- 如果不行，有时候需要使用`--force`强制推送，只要保证本地的版本是对的

## 杂项
只暂存部分文件提交后，未暂存文件的修改仍然保留在本地，状态还是已修改
