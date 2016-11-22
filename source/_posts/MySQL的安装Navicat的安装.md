---
title: MySQL以及Navicat的安装
tags: SQL学习
categories: 程序员必备
---
## 安装MySQL
1.首先安装MySQL有两种方式，第一种就是很简单的安装包安装点击安装，然后就无脑的往下装就好了。
第二种是zip格式的，我们需要自解压安装和配置，我就来讲解下，如何配置和安装。

2.首先解压到文件夹，放到你想放的位置，最好改一个你可以熟悉的文件名，这里我们把文件命名为MySQL Server 5.6.

3.解压后还不能直接使用MySQL,我们还需要配置下系统的环境，打开我的电脑->属性->高级系统设置->高级->环境变量。然后选择Path，在后面添加，注意是添加不是覆盖，注意是添加不是覆盖，在最后添加你mysql bin文件夹的路径（F:\zhaogaoxing\MySQL\MySQL Server 5.6\bin）
Path=......；F:\zhaogaoxing\MySQL\MySQL Server 5.6\bin
![Path%E9%85%8D%E7%BD%AE](http://obmrysrv0.bkt.clouddn.com/Path%E9%85%8D%E7%BD%AE.png)

4.接着还需要配置一下文件，mysql 5.6的默认配置文件是在F:\zhaogaoxing\MySQL\MySQL Server 5.6\my_default.ini,也可能需要自己建立一个my.ini文件，在其中修改或添加配置
[mysqld]
basedir=F:\zhaogaoxing\MySQL\MySQL Server 5.6(mysql所在目录)
datadir=F:\zhaogaoxing\MySQL\MySQL Server 5.6\data(mysql所在目录\data)
![mydefault](http://obmrysrv0.bkt.clouddn.com/mydefault.png)

5.然后我们就可以运行MySQL了，一定要用管理员身份运行cmd（这样才有足够的权限），进入F:\zhaogaoxing\MySQL\MySQL Server 5.6\bin文件夹中，输入mysqld -install,提示安装成功。
![mysqlroot](http://obmrysrv0.bkt.clouddn.com/mysqlroot.png)

6.安装成功后启动服务，在cmd中输入：net start mysql,服务启动成功，一定要在bin目录下操作，一定要配置好ini文件，如果还是不行（一般都可以了）就输入mysqld -remove 删除mysql,在输入mysqld -install重新安装。
成功启动服务以后输入 mysqld -u root -p,第一次登录没有密码直接回车跳过，登录成功，好了这样我们的mysql就安装好了，接着就要安装Navicat。
![mysqlroot2](http://obmrysrv0.bkt.clouddn.com/mysqlroot2.png)

## Navicat的安装
1.第一步很简单去找个Navicat的安装包，下载下来有很多，接着再下载一个PatchNavicat.exe破解程序，复制到Navicat安装目录下，双击执行就可以破解了。

2.根据安装提示一步一步的把Navicat安装好

3.查看mysql服务有没有打开，先打开任务管理器查看有没有mysql应用的进程
![Navicat1](http://obmrysrv0.bkt.clouddn.com/Navicat1.png)
如果没有,选择计算机-右键管理
![Navicat2](http://obmrysrv0.bkt.clouddn.com/Navicat2.png)

4.上面的几步完成以后，双击打开Navicat，点击连接
完成数据库的连接开心。
![Navicat](http://obmrysrv0.bkt.clouddn.com/Navicat.png)