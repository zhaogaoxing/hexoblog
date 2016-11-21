---
title: cmd使用方法（为自己mark的）
tags: cmd使用方法
categories: 程序员必备
cover_index: "http://obmrysrv0.bkt.clouddn.com/pig.jpg"
---
# cmd基础使用方法
>> cd 切换目录命令,后面跟文件名
cd.. 倒退回上一级
cls 清除屏幕上的所有命令
dir 查看当前目录的子文件夹
tree 当前目录的文件夹以树的形式显示出来
tree>a.txt 将回显的内容输入a.txt,没有会新建a.txt，有会覆盖内容
tree 后面也可以加文件夹的名称，显示该文件夹内容的回显
del 删除当前目录文件
attrib 更改和查看文件属性
md 添加一个文件夹
rd 删除一个文件夹
>> ">>"该符号为追加
shutdown 关机命令，参数一个一个解释
-i 打开图形操作界面
-l -r -s 关机命令，注销不支持远程
（logoff是注销命令，后面加ID号）
-c 增加注释，关机注释
-f 无警告强制关机，特凶残
-d 关机原因，写入日志，如：shutdown -d up
-t 关机时间，单位秒，默认30秒
-a 放弃关机，很有用，切记
exit 退出cmd
osk.exe 打开虚拟键盘
winchat.exe win自带的局域网聊天软件
regedit.exe 注册表

# color命令
>> 使用方法color**
第一个是背景色，第二个是文字颜色
color CA
背景红色，字体绿色

# format 格式化命令
>> /fs 指定格式化后的文件系统，FAT FAT32 NTFS
格式U盘，建议使用FAT32
硬盘，建议使用NTFS
/v 指定卷标
/q 快速格式化
/x 强制卸下该卷进行格式化
/a: ** 设置格式化后的单位大小
示范：C:\>format E:\fs:NTFS 

# cmd管理进程
>> tasklist 显示所有的进程
有一些进程是不能掐的如下：
WINLOGIN.EXE 系统会话，敢掐的都是天使
explorer.exe 资源管理器
iexplore.exe IE浏览器
taskmgr.exe 任务管理器
svchost.exe 很多服务，include PRC
taskkill 终止任务
taskkill/? 命令显示帮助
参数列表如图：
![cmdtaskkill1](http://obmrysrv0.bkt.clouddn.com/cmdtaskkill1.png)
![cmdtaskkill2](http://obmrysrv0.bkt.clouddn.com/cmdtaskkill2.png)
![cmdtaskkill3](http://obmrysrv0.bkt.clouddn.com/cmdtaskkill3.png)
![cmdtaskkill4](http://obmrysrv0.bkt.clouddn.com/cmdtaskkill4.png)

# 符号 * 的用法
>> 该符号的意思是代表不知道的多个字符
删除所有txt文件，可以输入 del * .txt即可
用法很多遍，也可用于你不清楚的扩展名
del *.* (像个表情)
ren 用于改名，文件名和扩展名都可以
ren a.txt a.vbs 将a.txt改名为a.vbs
ren *.txt *.vbs 就可以批量改名
copy 拷贝文件
copy a.txt b.txt 拷贝当前目录的a.txt并改名复制为b.txt放于当前目录
copy *.txt *.txt 可以批量复制

# net命令用法
>> net share  管理共享资源
输入 net share /? 会有该语句的用法，如图：
![netshare1](http://obmrysrv0.bkt.clouddn.com/netshare1.png)
使用不带参数的 net share显示本地计算机上的所有共享资源
![netshare2](http://obmrysrv0.bkt.clouddn.com/netshare2.png)
详细的用法还是比较复杂的我也在学习
1.建立共享
net share共享名=盘符（如F:）/users:用户数量（或者换成unlimited代表无限人数）/remark：“注记内容”
2.修改共享
net share 已有的共享 /users:用户数量（或者换成/unlimited代表无限人数） /remark：“注记内容”
3.删除共享
net share 共享名/del

## 关于服务的命令
>> net start 和 net stop
这里首先要用到services.msc(服务组策略)
首先在运行里输入 services.msc 回车，出现如图：
![services1](http://obmrysrv0.bkt.clouddn.com/services1.png)
所有的服务名都会出现
net start 服务名
net stop 服务名
可以开始和停止服务
同时，还有net pause以及net continue用法相同
下面的命令要注意使用，不要用到危险的地方
net use 将计算机与共享资源相连接
用法如下：
net use  \\远程电脑的ip地址或名字\连接方式或共享名称 “密码”/user:“用户名”
![netuse](http://obmrysrv0.bkt.clouddn.com/netuse.png)
IPC$的链接特点双方都必须开启IPC$管道
链接了远程电脑后可以使用 net time 查询时间
断开链接命令如下：
net use \\远程电脑名称或ip地址\连接方式 /del
建立链接以后就可以开始映射，把别人的硬盘当自己的用
还可以使用 at
用法为 at 时间 命令行

共享服务的专用命令
net statistics 和 net config

## 网络命令
ping
![cmdping1](http://obmrysrv0.bkt.clouddn.com/cmdping1.png)

# 小知识
>> 不同方向的斜杠意义不同
与位置有关的用 \
与参数有关的用 /
windows的最高管理员用户名默认为Administrator
牢记

# 未完待续
![prettylady2](http://obmrysrv0.bkt.clouddn.com/prettylady2.jpg)