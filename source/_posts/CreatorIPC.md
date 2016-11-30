---
title: IPC介绍--cocoscreator编辑器扩展
tag: CocosCreator
categroies: CocosCreator
---
## IPC简介
IPC是指进程间通信，Cocos Creator编辑器是基于Github开发的Electron内核，Electron是一个集成了Node.js和Chromimu的跨平台开发框架。  
Electron框架中，应用程序分为主进程和渲染进程。主进程负责管理平台的调度，包括窗口的开启关闭，菜单选项，基础对话框等等；每一个新开启的窗口就是一个独立的渲染进程。Electron中，每个进程独享自己的JavaScript内容，相互无法直接访问，所以当我们需要在进程之间传递数据时，就需要使用进程间通信（IPC）。  
[Electron's introduction document](https://github.com/electron/electron/blob/master/docs/tutorial/quick-start.md)这个文档很详细的介绍了主进程和渲染进程的关系，虽然是英文的。形象的说，Electron主进程就相当于Node.js服务端程序，当每一窗口（渲染进程）就相当于一份客户端界面程序。  

## 进程间通信（IPC）
进程间通信就是在一个进程中发消息，另一个进程监听消息的过程。Electron提供了进程间通信对应的模块ipcMain和ipcRenderer来帮助我们完成这个任务。这两个模块完成了非常基本的通信功能，不能满足编辑器，插件面板和主进程之间的通信要求，所以Cocos Creator在这之上进行了封装。

## IPC消息命名规范
可以随意的进行消息命名，但是还是希望有个规范。  
`'module-name:action-name'`  
`'package-name:action-name'` 

## 入口程序
每一个插件都可以指定一份入口程序，入口程序是在主进程中被执行的，我们通常在入口程序中：  
初始化扩展包  
执行后台操作程序  
调用Cococs Creatro主进程中的方法  
管理扩展面板的开启和关闭  
`'use strict';  
module.exports = {
	load(){
		console.log('package loaded');
	};
	unload () {
    console.log('package unloaded');
  },
};`  
load：当扩展包正确加载后，将会执行用户入口程序load函数，我们可以在这里做一些关于扩展包本身的初始化操作。  
unload：这是扩展包卸载的时候，调用unload函数，我们可以做一些扩展包的清理工作。

## IPC消息注册
在入口程序添加message字段，可以让扩展包在加载的时候进行主进程的IPC消息注册。  
`'use strict';
module.exports = {
  messages {
    'foo-bar' ( event ) { console.log('hello foobar'); },
    'scene:saved' ( event ) { console.log('scene saved!'); },
  },
};`

## 短命名消息
短命名消息是指消息名不带 ： 的消息，这种消息被视为该扩展包内的消息，在注册阶段，实际注册时会被写成 `${你的扩展包名}:${消息名}`。以上面的代码为例，假如我的扩展包名为“simple-demo”，那么“foo-bar”这个消息实际注册时会扩展为“simple-demo:foo-bar”。实际应用中，我们就可以通过`Editor.sendToPackage`函数发送IPC消息到主进程的指定扩展包的注册函数中。`Editor.sendToPackeage('simple-demo','foo-bar');`

## 全名消息
全名消息就是指消息名中带有 ：的消息命名方式。通过全名消息可以很清晰的知道这份消息是从哪个扩展包发出来的，更好的避免了消息冲突的问题。如上面的例子，`scene:saved	`这个消息是从scene这个内置扩展中发送的。

# 扩展主菜单
Cocos Creator的主菜单是可以自由扩展的。方法是在package.json中的main-menu字段里。加入自己的菜单路径和菜单设置选项。  
`{
  "main-menu": {
    "Examples/FooBar/Foo": {
      "message": "my-package:foo"
    },
    "Examples/FooBar/Bar": {
      "message": "my-package:bar"
    }
  }
}`

## 菜单路径
在主菜单中注册中，键值需要一份菜单路径，菜单路径是posix路径格式，使用/作为分隔符。

## i18n
菜单路径是支持i18n格式的路径，我们可以写`i18n:examples/i18n:foobar`,Cocos creator会帮助我们查找对应的i18n字符串。

## 菜单选项
我们已经使用message菜单选项。我们还可以使用：icon、accelerate、type等。