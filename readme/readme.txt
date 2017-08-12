初始化一个Git仓库，使用git init命令。

添加文件到Git仓库，分两步：

第一步，使用命令git add <file>，注意，可反复多次使用，添加多个文件；
第二步，使用命令git commit，完成。

git status告诉你有文件被修改过[提示add,commit]，用git diff可以查看修改内容

查看提交日志   $ git log --pretty=oneline [记录每次的  commit id 和 作者  日期]

回退到上一个版本 $ git reset --hard HEAD^,上上一个版本就是HEAD^^,往上100个版本HEAD~100

回退后，返回未来的版本id，$ git reset --hard 3628164

查看每次 commit 和 reset 的 id， git reflog

版本回退和前进都可以通过 $ git reset --hard commitid 完成

每次修改，如果不add到暂存区，那就不会加入到commit中

撤销工作区的修改
命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销，这里有两种情况：

一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

总之，就是让这个文件回到最近一次git commit或git add时的状态。

