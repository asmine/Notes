#Git学习笔记#

##从零开始创建一个git项目##

1、首先在自己的github上创建一个项目仓库repository，比如Notes，创建完成后拷贝该repository的地址：[https://github.com/asmine/Notes.git](https://github.com/asmine/Notes.git "https://github.com/asmine/Notes.git")

2、在本地创建Notes目录, mkdir Notes

3、进入Notes目录，git init

4、可以使用git status命令查看当前目录的情况，如有未提交的文件，则执行git add <filename>命令进行提交（该命令只是提交至本地暂存区），比如： git add git学习笔记.md

5、提交至本地仓库：git commit -m "commit git学习笔记.md file."

6、git remote add origin https://github.com/asmine/Notes.git

7、提交至远程仓库repository：git push -u origin master 

8、从远程仓库更新代码至本地：git pull https://github.com/asmine/Notes.git
