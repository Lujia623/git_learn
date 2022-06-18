## 第一个git实验

- `git add file`将文件添加到仓库
- `git commit -m "说明"`将文件提交到仓库
- `git diff`查看修改内容
- `git diff HEAD -- readme.txt`查看工作区和版本库里面最新版本的区别
- `git status`查看仓库状态
- `git log`查看提交日志
- `git log --pretty=oneline`查看提交日志,行显
- `git reset --hard HEAD^`回退到上一个版本
- `git reset --hard 3628164`回退到指定版本
- `git checkout -- readme.md`让这个文件回到最近一次git commit或git add时的状态