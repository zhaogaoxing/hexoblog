---
title: Linux基本操作命令(2)
tages: Linux
categories: Linux
---
## Clear
这个命令是用来清除屏幕的，和dos中的clr有相同的功能。

## Ln link
这是Linux中一个非常重要的命令，**它的功能是为某一个文件在另外一个位置建立一个不同的链接，这个命令最常用的参数是-s,具体的用法是：`ln 源文件 -s 目标文件`**。  
当我们在不同的目录下，用到相同的文件时，我们不需要在每一个需要的目录下都放一个必须相同的文件夹，我们只要在某个固定的位置，放上该文件，然后在其他目录下使用ln命令链接它就可以了，不用重复占用磁盘空间，比如：`ln/bin/less -s/user/local/bin/less`  
-s 是代号（symbolic）的意思。  
这里有两个注意点，第一，ln命令会保持每一处链接文件的同步性，只要你改动了任意一处，所以的同步文件都会被改变；第二，ln链接分两种一种是软链接ln -s ** **，它只会在你选定的位置上生成一个文件的镜像，不会占用磁盘的空间，第二种是硬链接ln ** ** ,没有参数-s，它会在你选定的位置上生成一个和源文件大小相同的文件，这两种链接的文件都是同步变化的。  
如果你用ls查看一个目录时，发现文件后面有一个@符号，这就是用ln生成的文件，用ls -l命令去查看，就可以看到显示的link路线了。

## Grep
用于查找文件中符合字符串的位置。比如：`e.g grep -nr "network_ssl" /`查找当前文件夹下所有文件内容，列出包含有network_ssl该字符串的行，并显示行号。