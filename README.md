# Git 使用说明

## 入门
Git 是一个免费的开源分布式版本控制系统，广泛用于软件开发和其他版本控制任务。要开始，首先在终端中安装 Git 然后配置用户信息。

```
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

## 基本命令
- `git init`: 初始化一个新的 Git 仓库。
- `git clone <repo>`: 从远程仓库克隆项目。
- `git add <file>`: 将文件添加到暂存区。
- `git commit -m "message"`: 提交更改。

## 分支管理
- `git branch`: 查看所有分支。
- `git branch <branch-name>`: 创建新分支。
- `git checkout <branch-name>`: 切换到某个分支。
- `git merge <branch-name>`: 合并分支。

## 提交历史
- `git log`: 查看提交历史。
- `git show <commit>`: 显示特定提交的详细信息。

## 远程操作
- `git remote -v`: 查看远程仓库。
- `git push`: 推送更改到远程仓库。
- `git pull`: 从远程仓库拉取更改。

## 高级技巧
- `git rebase`: 整理提交历史。
- `git stash`: 暂存当前更改。

这里是一些额外的资源： [Git 官方文档](https://git-scm.com/doc)