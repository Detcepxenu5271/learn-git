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

撤销修改

## 远程仓库

## 杂项
只暂存部分文件提交后，未暂存文件的修改仍然保留在本地，状态还是已修改
