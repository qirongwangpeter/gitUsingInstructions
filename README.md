Git 命令完整分情况讨论

情况一：教授/别人已经有仓库，你去克隆
bash# 1. 下载仓库到本地
git clone [仓库的HTTPS链接]

# 2. 进入仓库文件夹
cd [仓库名]

# 3. 创建并切换到自己的分支
git checkout -b qirong-fetchGeoCoord

# 4. 写代码...

# 5. 把改动放进待提交区
git add .

# 6. 提交
git commit -m "完成fetchGeoCoord"

# 7. 上传到GitHub
git push origin qirong-fetchGeoCoord

情况二：自己从零开始建一个新仓库
bash# 1. 先在 GitHub 网站上手动创建一个新仓库

# 2. 在本地项目文件夹里初始化 git
git init

# 3. 连接刚才在GitHub创建的仓库
git remote add origin [你的仓库HTTPS链接]

# 4. 把所有文件放进待提交区
git add .

# 5. 第一次提交
git commit -m "初始化项目"

# 6. 上传到GitHub（第一次要加 -u）
git push -u origin main

-u 的意思是"以后 push/pull 默认就用这个远程仓库"，只需要第一次加。


情况三：你本地有代码，但连错了仓库（你今天的情况）
bash# 1. 查看现在连的是哪个仓库
git remote -v

# 2. 断开错误的连接
git remote remove origin

# 3. 连接正确的仓库
git remote add origin [正确的HTTPS链接]

# 4. 先拉取远程仓库的代码（避免冲突）
git pull origin main

# 5. 再推上去
git push origin main

情况四：队友已经推了新代码，你要更新本地
bash# 1. 先切换到 main 分支
git checkout main

# 2. 拉取最新代码
git pull origin main

# 3. 切回自己的分支继续工作
git checkout qirong-fetchGeoCoord

情况五：写错了，想撤销
bash# 文件改了但还没 add：直接撤销文件修改
git restore [文件名]

# 已经 add 了，但还没 commit：退回到未add状态
git restore --staged [文件名]

# 已经 commit 了：撤销最近一次commit（代码还在，只是取消提交）
git reset --soft HEAD~1

情况六：查看各种状态
bashgit status          # 查看哪些文件待提交/未追踪
git branch          # 查看当前在哪个分支
git remote -v       # 查看连接的远程仓库
git log             # 查看完整commit历史
git log --oneline   # 查看简洁版commit历史

总流程对比
情况一（克隆别人的）：
clone → checkout -b → 写代码 → add → commit → push

情况二（自己新建）：
GitHub建仓库 → git init → remote add → add → commit → push -u

情况三（连错了）：
remote remove → remote add → pull → push

情况四（同步队友代码）：
checkout main → pull → checkout 自己的分支
