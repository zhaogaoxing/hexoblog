---
title: AS3游戏中常用的类
tags: ActionScript
categories: ActionScript
---
#object类
当你创建一般对象时，你可以将任何类型的信息储存在该对象中；
也可以用它来保存任何自定义方法。

#Color类
Color类，一般用来改变游戏各种显示状态的颜色。

#Sound类
Sound类，游戏中用来处理各种交互时的声音。

#Mouse类
Mouse类，游戏中处理鼠标事件。
在flash中新建一个mc元件，在该mc上加入以下代码。
mc会跟随你的鼠标。
`onClipEvent(enterFrame)
{
_x += (_root._xmouse - _x)/10;
_y += (_root._ymouse - _y)/10;
}`

#Key类
Key类，游戏中处理按键事件
if(Key.isdo(Key.LEFT)){}
if(Key.isdo(Key.SPACE)){}

#Math类
Math类，游戏中用来处理数学计算

#String类
String类，游戏中按一定要求操作字符串
如: 利用字符串的split()来分析数据包
数据包格式为t,I'm asFox
`chatData:String = "t,I'm asFox" //t标志是聊天信息，不同的信息可以用不同的标志区分。
myData = chatData.split(",")

for(var i=0;i if(myData[0]=="t"))
{
trace("这是一个聊天数据包");
trace("这是聊天内容"+myData[1]);
}

#Array类
Array类，游戏中处理各种数组
使用数组创建游戏的地图
`screen_width = 224;
screen_height = 228;

tile_width = 16;
tile_height = 16;

tile_vert = screen_width/tile_width;
tile_hort = screen_height/tile_height;
//二维数组地图
map = [[10,10,10,10,10,10,10,10,10],
[10,10,10,10,10,10,10,10,10],
[10,10,10,10,10,10,10,10,10],
[10,10,10,10,10,10,10,10,10],
[10,10,10,10,10,10,10,10,10],
[10,10,10,10,10,10,10,10,10],
[10,10,10,10,10,10,10,10,10],
[10,10,10,10,10,10,10,10,10],
[11,10,10,10,10,10,10,10,11],
[11,10,10,10,10,10,10,10,11],
[11,10,10,28,29,30,10,10,11],
[13,13,13,13,13,13,13,13,13],
[13,13,13,13,13,13,13,13,13]];

this.attachMovie("empty","cont",1);//empty是一个连接名叫"empty"的空影片剪辑
for(y=0;y for(x=0;x var t = "tile"+x+"_"+y;
cont.attachMovie("tile",t,y*map[0].length+x);//向cont中添加砖块
cont[t]._x = x*tile_width;
cont[t]._y = y*tile_height;
cont[t].gotoAndStop(map[y][x]);//砖块跳到相应的帧。
}
}`

#XML类及XMLsccket

