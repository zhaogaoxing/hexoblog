---
title: as中有趣的算法
tag: ActionScript
categories: ActionScript
cover_index: "http://obmrysrv0.bkt.clouddn.com/9999.jpg"
---
# AS中不太常见的代码写法
1.`mc.gotoAndPlay(Math.random()*10>>0);`
`Math.random()*10` 取10以内带小数的随机数。
“>>”是移位符号 “>>0” 的功能是去除小数点后的数。
所以这行代码的意思是获取10以内的随机整数。

用在加载进度条中
`trace((已经加载的字节数/总字节数)*100>>0+"%");`

2.`if(i&1){}`
i&1的意思就是判断i是奇数还是偶数
如果是奇数i的2进制表示最后一位是1,i&1=1,为真
偶数i的2进制表示最后一位是0，i&1=0,为假。

3.`var a:Array = new Array();
for(var i:int=0;i<10;a.push(i++)){}`
该循环执行后a数组的值为0，1，2，3，4，5，6，7，8，9
一个简化程序的方法

4.`var temp:Number = mouseX;
stage.addEventListener(MouseEvent.MOUSE_MOVE,moveHandler);
function moveHandler(e:MouseEvent):void
{
var d:Number = (-temp+(temp=mouseX));
}`
功能为获取鼠标移动的距离d
可以用在鼠标拖拽窗体或者鼠标拖拽游戏上
还可以改成:
`Mouse.hide();
var temp:Number = mouseX;
stage.addEventListener(MouseEvent.MOUSE_MOVE,moveHandler);
function moveHandler(e:MouseEvent):void
{
var d:Number = (-temp+(temp=mouseX));
spriteMouse.x +=d;
e.updateAfterEvent();
}`

5.`function fn1()
{
trace("1");
}
function fn2()
{
trace("2");
}
([fn1,fn2][Math.random()*2>>0])();`
随机执行函数的命令

6.`var a:int=3;
if(a>0&&(trace("a is positive number"),a&1))
{
trace("a is positive odd number");
}`
先执行a>0真，再执行 trace最后判断a是不是奇数，
这里的逗号表达式是从左向右执行的。



