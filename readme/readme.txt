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

撤销暂存区的修改
用命令git reset HEAD readme.txt可以把暂存区的修改撤销掉（unstage），重新放回工作区
git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用HEAD时，表示最新的版本。
暂存区变成最新版本，即为空。

撤销版本库的修改（误提交，但没有push时）
版本回退$ git reset --hard commitid

删除文件$ git rm test.txt删除完
要么提交 $ git commit -m "remove test.txt"
要么撤销删除  $ git checkout -- test.txt

ADD key to github
假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub
创建SSH Key：$ ssh-keygen -t rsa -C "flytonus@sina.com"
在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人
登陆GitHub，打开“Account settings”，“SSH Keys”页面：
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容

在 本地关联远程库，$ git remote add origin git@github.com:flytian/learngit.git
添加后，远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库

把本地库的内容推送到远程，$ git push -u origin master
用git push命令，实际上是把当前分支master推送到远程
第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，
还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令
添加远程库

推送成功后，可以立刻在GitHub页面中看到远程库的内容已经和本地一模一样：
从现在起，只要本地作了提交，就可以通过命令：

$ git push origin master
把本地master分支的最新修改推送至GitHub

