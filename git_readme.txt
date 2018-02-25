Git is a version control system.
Git is free software.

小结：
1）先建立一个空的文件夹。进入到该新建的文件夹里。
2）初始化一个Git仓库，使用git init 命令
3）添加文件到Git仓库，分为两步：
第一步：使用命令 git add <file> ,注意，可反复多次使用，添加多个文件。
第二部：使用命令 git commit 完成。

===》每次修改文件后，要重新git add <file> 然后git commit 完成。

小结二：
1)HEAD 指向的版本就是当前版本，因此，git 允许我们再版本的历史质检穿梭，使用命令
git reset --hard commit_id.
2)穿梭前，用git log 可以查看提交历史，以便确定要退到哪个版本。
3）要重返未来，用git reflog 查看命令历史，以便确定要回到未来哪个版本。


小结三：
工作区<Working Directory>
就是电脑里能看到的目录，比如我的git_respository 文件夹就是一个工作区。
版本库<respository>
工作区有一个隐藏目录.git， 这个不算工作区，而是Git 的版本库。
Git 的版本库里存了很多东西，其中最重要的就是stage（或者叫做index)的暂存区，还有Git 为我们自动常见的第一个分支master。

***把文件往Git 版本库里添加的时候，是分两步执行的：
第一步是用git add 把文件添加进去，实际上就是把文件修改添加到暂存区。
第二步是用git commit 提交更改，实际上就是把暂存区的所有内容提交到当前分支。

因为我们创建Git 版本库时，Git自动为我们创建了唯一一个master 分支，所以，现在，git commit 就是往master分支上提交更改。
可以简单的理解为，需要提交的文件修改统统放到暂存区，然后一次性提交暂存区的所有修改。

小结四：
Git 是如何跟踪修改的，每次修改，如果不add到暂存区，那就不会加入到commit中。