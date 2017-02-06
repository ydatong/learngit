#### git学习笔记

##### 1.创建版本库

版本库可以理解为项目的目录，git可以管理这个目录下面的所有文件。

通过 `git init` 将目录变为git可以管理的仓库

通过  `git add`将文件添加到git仓库 （实际上是把文件修改添加到暂存区）

`git add`命令实际上是把所有要提交的修改存放到暂存区，然后执行`git commit`就可以一次性把暂存区的所有修改提交到分之上面

通过 `git commit -m `将文件提交到git仓库 （实际上是把暂存区的所有内容提交到当前分之）

为什么git添加文件需要add和commit两个步骤？因为commit可以一次提交多个文件，所以可以多次add不同的文件。

通过 `git status` 来查看仓库文件的状态

通过 `git diff`来查看文件修改内容

通过 `git log`来查看修改日志

通过 `git reset --hard HEAD^`来回退到上一个版本

通过 `git reset --hard 版本号` 来退回到某个版本

HEAD指向的版本就是当前的版本s

##### 工作区和暂存区

当前的工作目录就是工作区

工作区有一个隐藏目录.git，这个不算工作区，而是git的版本库

git的版本库里面存放了很多东西，其中最重要的就是stage（暂存区），还有git为我们自动创建的第一个分之master，以及指向master的一个指针叫HEAD

通过 `git checkout -- 文件名`可以丢弃工作区的修改 ， 就是让文件回到最近一次`git commit`或者`git add`的状态

注意 `git checkout -- 文件名`中的 -- 很重要，如果没有 -- 就变成了 “切换到另一个分支”的命令

通过 `git reset HEAD file`可以把暂存区的修改撤销，重新放回工作区

删除某个文件之后，通过`git rm 文件名`删除，然后`git commit`提交

##### 远程仓库

[为github账号添加SSH keys](http://blog.csdn.net/keyboardota/article/details/7603630)


`git remote add origin git@github.com:ydatong/learngit.git`将本地的仓库与远程库相关联

远程库的名称就是 origin ，这是git默认的叫法，也可以改成别的。

然后通过 `git push -u origin master`将本地库所有的内容推送到远程库上面

由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

后面只要本地做了提交，就可以通过 `git push origin master` 把本地master分之的最新修改推送至github了。

1




























