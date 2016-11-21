---
title: MFC中的问题和解决方法
tags: MFC
categories: 程序员必备
cover_index: "http://obmrysrv0.bkt.clouddn.com/pig.jpg"
---
这是我在使用win32以及MFC中遇到的问题，
我把它们集中起来，让自己好好记住

# 使用VS2013添加控件的工具箱的位置
它自己不会显示被隐藏了，真的烦
![win32](http://obmrysrv0.bkt.clouddn.com/win32.png)
但是我终于找到了在这里，点击旁边的下拉菜单就可以看到工具箱，勾选就可以了，vs真的佩服。

# 使用win32时出现的兼容问题（字符兼容问题应该是个通解）
error C2664: “CWnd::MessageBoxW”: 不能将参数1 从“const char [3]”转换为“LPCTSTR” 错误 2 error C2664: “inet_addr”: 不能将参数 1 从“_TCHAR *”转换为“const char *” d:\vc program\clienttcp\clienttcp\clienttcp.cpp 29 原因：有的VS默认的"使用 Unicode 字符集"
解决：在你建立的解决方案的工程文件的属性看到选"配置属性"的"字符集"请选择"使用多字节字符集"就可以了。
![win322](http://obmrysrv0.bkt.clouddn.com/win322.png)

未完待续！！！！