---
title: USB开发
tag: USB
categories: USB
---
## USB3.0电缆引线定义
VBUS：一般为红色，+5伏电源的输出或者输入
D-：一般为白色，USB差分负信号数据线的输入或者输出
D+：一般为绿色，USB差分正信号数据线的输入或者输出
GND：一般为黑色，USB接口的地线
SSRX-：未做要求，超高速USB3.0数据输入引脚
SSRX+：未作要求，超高。速USB3.0数据输入引脚
SSTX-：未作要求，超高速USB3.0数据输出引脚
SSTX+：未作要求，超高速USB3.0数据输出引脚
Shell：屏蔽层

## USB连接器
USB总线规范规定了多种USB连接器，主要包括A型和B型两类，USB连接器的插座和插头相互匹配。一般来说，A型插座总是作为USB主机或者USB集线器的下行端口，所以A型插头总是指向上行的USB主机。B型插座总是作为USB设备或USB集线器的上行端口，所以B型插头总是指向下行USB设备或集线器。

### USB3.0标准A型接口
超高速USB3.0采用了9针脚设计，其中4个与USB2.0的形状、定义相同，另外5根完全为超高速USB3.0设计。

### USB3.0标准B型接口

### USB3.0Micro型接口
共有10根信号线和一个屏蔽层

## USB总线设备类规范
包括三个部分：USB基本规范，USB设备类规范和USB HOST控制器规范，对于一般的USB设备开发者开说，最关心的是USB设备类规范。

### USB设备类规范
Audio Device
Communications Device
Chip/Smart Card Interface Device
Device Fireware Upgrade
Image Device
Human Interface Device
IrDA Bridge Device
Mass Storage Device
Physical Interface Device
Power Device
Printer Class
Monitor Device
Custom Device

### USB系统结构
1.功能层
主要负责数据传输等特点的操作，功能层由USB设备的功能单元和对应的USB主机程序实现组成。按照双方通信的类型，分为如下4种：
控制传输：主要用于传输少量的对时间和速率都没有要求的数据。一般用于USB主机读取或设置USB设备的配置信息。
中断传输：用于传输少量对传输时间具有周期性要求的数据。在鼠标和键盘等HID人机接口设备中经常使用。
快传输：用于传输大量的，对传输时间和速率没有严格要求的数据。
同步传输：用于传输大量的，而且传输时间具有周期性，速率恒定的数据。

2.USB设备层
主要用于管理USB设备，分配USB地址、读取设备描述符等。在这一层，可以是USB主机获得该USB设备的能力。

3.USB总线接口层
主要用于实现USB主机和USB设备之间的数据传输。在USB协议中，USB总线接口使用NRZI编码（反向非零编码）来传输数据。   

## USB接口开发
USB系统开发可以分为3类：USB主控制器的开发，USB集线器的开发和USB功能设备的开发。一般以USB功能设备开发最为广泛。

### USB硬件开发

### USB驱动开发

### USB软件开发

