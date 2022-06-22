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
