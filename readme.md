## git常用命令

- `git add file`将文件添加到仓库
- `git commit -m "说明"`将文件提交到仓库
- `git diff`查看修改内容
- `git diff HEAD -- readme.txt`查看工作区和版本库里面最新版本的区别
- `git status`查看仓库状态
- `git log`查看提交日志
- `git log --pretty=oneline`查看提交日志,行显
- `git reset --hard HEAD^`回退到上一个版本
- `git reset --hard 3628164`回退到指定版本
- `git checkout -- readme.md`让这个文件回到最近一次git commit或git add时的状态,要有`--`,不然变成创建新分支
- 撤销已经添加到暂存区单位commit的修改
    1. 先使用`git reset head readme.md`命令
    2. 再使用`git checkout -- readme.md`命令
- `git rm <file>`删除文件
- `git push -u origin master`push代码到远程分支上
- `git remote add origin git@github.com:michaelliao/learngit.git`关联远程库
- `git push -u origin master`第一次推送master分支的所有内容
- `git push origin master`后续每次在本地提交修改后,可以直接向远程库提交修改
- 在初始化仓库时,最好的方式是从远程库初始化仓库,然后`clone`到本地
- `git branch dev`创建分支
- `git checkout dev`切换分支
- `git checkout -b dev`创建并且切换分支
- `git branch`命令查看当前分支
- `git merge dev`用于合并分支到当前分支(合并dev分支到master分支上--->Fast-forward)
- `git branch -d dev`删除分支
- `git log --graph --pretty=oneline --abbrev-commit`查看分支合并图
- `git branch -d dev`删除分支
- `git  merge --no-ff -m "merge with no-ff" dev`此种合并方式包含commit信息,即使删除分支后仍然保留有分支信息,合并后的历史有分支信息
- `git stash`将当前现场的工作储藏起来,方便以后恢复现场后可以继续工作
- `git stash list`查看工作现场存储情况
- `git stash apply`恢复工作现场,但是恢复后工作现场的内容并不删除,后面可以使用`git stash drop`来删除
- `git stash pop`恢复现场的同时将`stash`内容一并删除
- `git stash apply stash@{0}`可以恢复指定的`stash`
- `git branch -D dev`强行删除分支(新建的分支内容有改动,但是未完成合并)
- `git push origin dev`推送指定分支到远程库
- `git push origin :dev`推送一个空的分支到远程分支上,相当于删除远程分支
- `git pull <远程主机名> <远程分支名>:<本地分支名>`取回远程主机某个分支的更新,再与本地的指定的某个分支合并
- `git pull origin dev`将远程dev分支和当前分支合并
- `git branch --set-upstream-to=origin/dev`指定本地分支和远程分支链接,本地当前分支追踪远程`dev`分支
- `git branch --set-upstream dev origin/dev`指定本地分支和远程分支链接,本地`dev`追踪`origin/dev`
- `git remote -v`查看远程库分支信息
- 从本第推送分支,使用`git push origin dev`,如果推送失败,则需要pull,如果有冲突,则需要解决冲突然后再本地提交,再推送到远程分支上
- `git checkout -b dev origin/dev`新建一个分支`dev`,并将其和远程库分支`dev`建立跟踪关系
- `git branch -vv`查看本地分支和远程库分支的追踪关系
- `git log --pretty=oneline --abbrev-commit`查找`commit`历史,以每次`commit`信息显示
- `git tag <commit id>`将前面的`commit`打上标签
- `git tag -a v1.0 -m "说明" <commit id>`创建带说明的标签,`-a`用来指定标签,`-m`指定说明文字
- `git show <tag id>`查看标签信息(如输入`git show tag v1.0`将显示标签`v1.0`的信息)
- `git push origin v1.1`推送`v1.1`标签到远程
- `git push origin --tags`推送所有本地标签到远程
- `git tag -d <tag id>`删除本地标签
- `git push origin :v1.1`或者`git push origin :tags/v1.1`
- `git config --global clore.ui true`让`git`显示颜色,可以看起来更加醒目

### 问题

- 使用`git push -u origin master`命令报错如下:
    `! [rejected] master -> master (fetch first)`,原因是远程库版本和本地库版本不一致,可以使用`git push -f origin master`强制推送本地库版本到远程库(谨慎使用),建议先`fecth`后合并再推送到远程库
