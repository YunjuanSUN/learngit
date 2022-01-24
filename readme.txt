Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.

创建版本库
//git init 这个目录变成Git可以管理的仓库  
//git add <file> 把文件添加到仓库 
//git commit -m "wrote a readme file" 把文件提交到仓库 

版本回退
//git status 让我们时刻掌握仓库当前的状态
//git diff 看看具体修改了什么内容需要用
//git log 显示从最近到最远的提交日志 以便确定要回退到哪个版本。
//git reflog 查看命令历史，以便确定要回到未来的哪个版本

撤销修改
//git reset --hard commit_id 允许我们在版本的历史之间穿梭
//git reset --hard HEAD^ 要把当前版本回退到上一个版本
//git checkout -- file 丢弃工作区的修改
//git reset HEAD <file> 把暂存区的修改撤销掉（unstage）重新放回工作区
//1.丢弃工作区的修改 git checkout -- file
//2.丢弃暂存区的修改 git reset HEAD <file>
//3.撤销修改到版本库 git reset --hard commit_id

删除文件
//git rm <file> 从版本库中删除该文件
//用命令git rm删掉且git commit
//git checkout -- <file>把误删的文件恢复到最新版本

远程仓库
//创建SSH Key ssh-keygen -t rsa -C "email"
//在本地的仓库下运行命令关联一个远程库
git remote add origin git@github.com:github_name/repository_name.git
//把本地库的所有内容推送到远程库上
git push -u origin master
//解除了本地和远程的绑定关系
git remote rm origin

从远程库克隆
//登陆GitHub，创建一个新的仓库
//git clone git@github.com:github_name/repository_name.git
//Git支持多种协议，包括https，但ssh协议速度最快

创建与合并分支
//git switch -c dev 创建dev分支，然后切换到dev分支
//git switch master 切换回master分支
//git merge dev 把dev分支的工作成果合并到master分支上
//git branch -d dev 删除dev分支

解决冲突
//解决冲突就是把Git合并失败的文件手动编辑为我们希望的内容再提交
//用git log --graph命令可以看到分支合并图

分支管理策略
//合并dev分支，请注意--no-ff参数，表示禁用Fast forward
git merge --no-ff -m "merged bug fix 101" issue-101
//用git log看分支历史 
//git stash 把当前工作现场“储藏”起来，等以后恢复现场后继续工作
//git stash pop 恢复的同时把stash内容也删了
//git cherry-pick <commit> 把提交的修改“复制”到当前分支
//git push origin <branch_name> 推送分支

多人协作
//git branch --set-upstream-to=origin/<branch> dev 设置dev和origin/dev的链接
//git pull 先用git-pull把提交从origin/dev抓下来，然后在本地解决冲突再推送
//git push origin branch-name

创建标签
//git log --pretty=oneline --abbrev-commit
//git tag <tag_name> <commit_id>
//git tag -a v0.1 -m "version 0.1 released" 1094adb
//git show <tagname>可以看到说明文字

//git push origin <tagname> 推送某个标签到远程
//git push origin --tags 一次性推送全部尚未推送到远程的本地标签

标签已经推送到远程
//git tag -d <tagname>
//git push origin :refs/tags/<tagname>

//git remote -v查看远程库信息
//git remote add github git@github.com:michaelliao/learngit.git
//git remote add gitee git@gitee.com:liaoxuefeng/learngit.git




 
 




