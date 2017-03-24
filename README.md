#git命令总结
###git基础命令
1.cd 进入某某目录，example: cd d: 进入d盘。`pwd`查看当前目录

2.在某个目录下使用命`git init`,这个目录就成为了一个仓库，目录中的所有文件就可以被git管理了。

3.使用`git add`加文件名添加文件。

4.第四部，使用`git commit -m "操作说明"`保存

5.`git status`查看状态，`git diff`查看不同

6.修改的时候要提交使用的也是git add git commit liang'bu这两步

7.使用`git log`查看历史记录 使用`git log --pretty="commit id"`查看特定版本号
 
8.使用`git reset --hard HEAD^`退回到特定版本，退回上100个版本为HEAD~100。`git set --hard +commit号`可以退回到特定版本
 
9.`git reflog`在关闭电脑之后仍然可以找到历史的各个版本号用于退回
 
10.**暂存区的概念**，git add 是把内容先放到暂存区。git commit就是放到分支上。
 
11.如果只是修改了内容，没有git add 和git commit 可以通过 `git checkout -- +文件名丢弃`。

12.如果已经add了，可以通过git reset HEAD file和checkout撤销

13.如果add、和commit之后就可以版本回退。

14.**删除内容**。删了文件之后，实际是把工作区的文件删除了，如果要把版本库的文件也删除，则使用git rm + 文件名。然后再git commit。如果是误删的则可以，checkout 回复。
###远程仓库
1.将本地git仓库添加到远程github仓库，并用这两个仓库进行远程同步。先在github上建立一个同名的repository，然后使用命令`$ git remote add origin git@github.com:+github的用户名/+repository名称.git`，然后使用`$ git push -u origin master`,以后再更新用`$ git push origin master`即可

2.将远程库克隆到本地使用`git clone`
###分支
1.创建新的分支并切换到该分支`git checkout -b + 你要创建的分支名称`。其中创建新的分支命令为`git branch +分支的名字`，切换分支`git checkout +分支的名称`

2.查看当前分支 `git branch`

3.合并某分支到当前分支`git merge+该分支的名称`

4.删除分支 `git branch -d +要删除的分支名称`

7.如果master和其他分支都做了修改并且提交的话。在用git merge进行分支合并会失败。所以要先进行处理。会提示出分支的情况，所以需要进行删除等操作。

5.通常，合并分支时，如果可能，Git会用Fast forward模式，但这种模式下，删除分支后，会丢掉分支信息。使用`git merge --no-ff -m "合并dev" dev
`
6.有bug要修复时，先把工作区的内容隐藏，使用`git stash`,然后切换到master分支，创建新的分支来修复，然后合并到master。删除修复分支，最后切换到工作分支，使用`git stash pop`显示刚刚隐藏的内容。

    
