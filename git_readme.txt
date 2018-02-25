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


git has a mutable index called stage.