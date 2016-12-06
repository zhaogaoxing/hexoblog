---
title: 扩展编辑器--cocoscreator编辑器扩展
tag: CocosCreator
categories: CocosCreator
---
## 扩展编辑器面板
CocosCreator中允许用户定义一份面板窗口做编辑器的UI交互。

## 定义方法
在插件的package.json文件中定义panel字段。  
`{
  "name": "simple-package",
  "panel": {
    "main": "index.js",
    "type": "dockable",
    "title": "Simple Panel",
    "width": 400,
    "height": 300
  }
}`   
通过定义panel字段，并申明面板type为dockable我们就可以获得该面板窗口，通过定义main字段我们可以为我们的面板窗口指定一份入口程序。

## 定义入口程序
定义一份面板的入口程序，我们要通过Editor.Panel.extend()函数来注册面板。  

![CocosCreator1](http://obmrysrv0.bkt.clouddn.com/CocosCreator1.png)  

经过上述操作后，我们就可以通过调用`Editor.Panel.open('simple-package')`激活我们的界面。更多的界面定义选项，阅读[面板定义参考](http://www.cocos.com/docs/creator/extension/reference/panel-reference.html)

## 在主菜单中添加打开面板选项
我们通常把打开窗口的方法注册到主菜单中，通过发消息给我们的插件主进程代码来完成，我们需要在package.json中注册主进程入口函数和主菜单选项。
![CocosCreator2](http://obmrysrv0.bkt.clouddn.com/CocosCreator2.png)  

在main.js中我们做如下定义。
![CocosCreator3](http://obmrysrv0.bkt.clouddn.com/CocosCreator3.png)

然后就可以通过菜单栏来打开我们自己的面板。
![CocosCreator4](http://obmrysrv0.bkt.clouddn.com/CocosCreator4.png)