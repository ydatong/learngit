#### git学习笔记

##### 1.创建版本库

版本库可以理解为项目的目录，git可以管理这个目录下面的所有文件。

通过 `git init` 将目录变为git可以管理的仓库

通过  `git add`将文件添加到git仓库

通过 `git commit -m `将文件提交到git仓库

为什么git添加文件需要add和commit两个步骤？因为commit可以一次提交多个文件，所以可以多次add不同的文件。

通过 `git status` 来查看仓库文件的状态