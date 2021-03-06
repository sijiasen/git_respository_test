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

小结五：
git checkout -- readme.txt 意思是，把readme.txt 文件在工作区的修改全部撤销，有两种情况：
一种是：readme.txt 自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态。
一种是：readme.txt 已经添加到暂存区，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

小结六：
假设你不但改错了东西，还从暂存区提交到了版本库，怎么办，使用版本回退到上一个版本，不过这是有条件的，，就是
你还没有把自己的本地版本库推送到远程。Git 是分布式版本控制系统，一旦把xxx提交推送到远程版本库，就真惨了。。。。


场景1： 当改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用git checkout -- file。
场景2： 当不但改乱了某个工作区某个文件的内容，还添加到了暂存区，想丢弃修改，分为两步，第一步用命令
git reset HEAD file，回到场景1，再用git checkout -- file 放弃工作区修改。
场景3： 已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

小结七：
git checkout -- test.txt 
git checkout 其实就是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以”一键还原“

命令 git rm 用于删除一个文件，如果一个文件已经被提交到版本库，那么永远不用担心误删，但是要小心，
只能恢复文件到最新版本，会丢失最近一次提交后所修改的内容。

小结八：
要关联一个远程库，使用命令git remote add origin git@github.com:sijiasen/git_respository_test.git
关联后，使用命令git push -u origin master 第一次推送master 分支所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令git push origin master 推送最新修改；

分布式版本系统的最大好处之一是在本地完全不需要考虑远程库的存在，也就是有没有联网都可以
正常工作，而SVN在没有联网的时候是拒绝干活的！当有网络的时候，再把本地提交推送一下就完成同步了，方便。！

小结九：
要克隆一个仓库，首先必须知道仓库的地址，然后使用git clone 命令克隆。
Git 支持多种协议，包括https，但通过ssh 支持的原生git协议速度最快。

小结十：
Git 鼓励大量使用分支：
查看分支：git branch
创建分支：git branch <name>
切换分支：git checkout <name>
创建+切换：git checkout -b <name>
合并某分支到当前分支： git merge <name>
删除分支：git branch -d <name>










