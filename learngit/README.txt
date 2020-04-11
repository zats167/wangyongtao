

创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录：

$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit

第一步，用命令git add告诉 Git，把文件添加到仓库：

$ git add readme.txt  或者 echo “文本内容” > readme.txt
执行上面的命令，没有任何显示，这就对了，Unix 的哲学是“没有消息就是好消息”，说明添加成功。

第二步，用命令git commit告诉 Git，把文件提交到仓库：

$ git commit -m "wrote a readme file"
[master (root-commit) cb926e7] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 readme.txt

git status命令可以让我们时刻掌握仓库当前的状态，上面的命令告诉我们，readme.txt 被修改过了，但还没有准备提交的修改。

虽然 Git 告诉我们 readme.txt 被修改了，但如果能看看具体修改了什么内容，自然是很好的。比如你休假两周从国外回来，第一天上班时，已经记不清上次怎么修改的 readme.txt，所以，需要用git diff这个命令看看：

$ git reset --hard 3628164
在 Git 中，总是有后悔药可以吃的。当你用$ git reset --hard HEAD^回退到add distributed版本时，再想恢复到append GPL，就必须找到append GPL的commit id。Git 提供了一个命令git reflog用来记录你的每一次命令：
$ cat readme.txt
第一步是用git add把文件添加进去，实际上就是把文件修改添加到暂存区；

第二步是用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。