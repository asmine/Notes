#Git学习笔记#

##从零开始创建一个git项目##

1、首先在自己的github上创建一个项目仓库repository，比如Notes，创建完成后拷贝该repository的地址：[https://github.com/asmine/Notes.git](https://github.com/asmine/Notes.git "https://github.com/asmine/Notes.git")

2、在本地创建Notes目录, 

	mkdir Notes

3、进入Notes目录，

	git init

4、可以使用

	git status
查看当前目录的情况，如有未提交的文件，则执行git add filename 命令进行提交（该命令只是提交至本地暂存区），比如：
 
	git add git学习笔记.md

5、提交至本地仓库：

	git commit -m "commit git学习笔记.md file."

6、添加远程仓库：

	git remote add origin https://github.com/asmine/Notes.git

7、提交至远程仓库repository：

	git push -u origin master 

8、从远程仓库更新代码至本地：

	git pull https://github.com/asmine/Notes.git

9、删除文件：

	git rm filename

10、一般情况下，可能会有一些文件无需纳入git的管理，也不希望它们总出现在未跟踪文件列表，在这种情况下，可以创建一个名为.gitignore的文件，列出要忽略的文件模式.

11、比较文件:

	git diff

注意，git diff本身只显示尚未暂存的改动，而不是自上次提交以来所做的所有改动，如果暂存了所有更新过的文件，git diff则什么也没有.

12、跳过使用暂存区：只要在提交时， 

	git commit加上 -a选项，

git就会的自动把所有已经跟踪过的文件暂存起来并一并提交，从而跳过git add步骤

13、重命名文件：

	git mv filename_from filename_to

   git mv命令实际相当于运行了下面三个命令：

	mv filename_from filename_to

	git rm filename_from

	git add filename_to

14、查看提交历史：

	git log

不加任何参数的话，会按提交时间列出所有的更新，最近的更新排在最上面

  -p  用来显示每次提交的内容差异

  -2  仅显示最近两次提交

Table 2. git log 的常用选项	说明

-p  按补丁格式显示每个更新之间的差异。

--stat  显示每次更新的文件修改统计信息。

--shortstat  只显示 --stat 中最后的行数修改添加移除统计。

--name-only  仅在提交信息后显示已修改的文件清单。

--name-status  显示新增、修改、删除的文件清单。

--abbrev-commit  仅显示 SHA-1 的前几个字符，而非所有的 40 个字符。

--relative-date  使用较短的相对时间显示（比如，“2 weeks ago”）。

--graph  显示 ASCII 图形表示的分支合并历史。

--pretty  使用其他格式显示历史提交信息。可用的选项包括 oneline，short，full，fuller 和 format（后跟指定格式）。

15、取消暂存的文件：

	git reset HEAD filename

   撤销对文件的修改（注意，此命令会修改**工作区**的文件内容，对那个文件做的任何修改都会消失--危险命令）：

	git checkout -- filename

16、查看远程仓库repository： 

	git remote

也可以指定-v参数，会显示需要读写远程仓库使用的git保存的简写与其对应的URL

17、添加远程仓库：
 
    git remote add **shortname** **url** 
 
   推送到远程仓库： git push [remote-name] [branch-name],日字旁想将master分支推送到origin服务器，运行该命令：

    git push origin master

   查看远程仓库：

	git remote show [remote-name]
