# uLanding 雷达
官网英文原文地址：[http://dev.px4.io/uart-ulanding-radar.html](http://dev.px4.io/uart-ulanding-radar.html)

uLanding 雷达是 \[Aerotenna\]\([http://aerotenna.com/sensors/\](http://aerotenna.com/sensors/\)\) 的产品，可用于测量与物体之间的距离。
## 启用硬件驱动程序

目前，一些OS NuttX系统的硬件支持该雷达设备，并为其提供串行端口接口。由于某些硬件上的闪存空间很小，可能需要自己构建驱动程序。为此，请将以下行添加到与要构建的目标对应的cmake配置文件中：

```
drivers/ulanding
```

所有配置文件位于 [此处](https://github.com/PX4/Firmware/tree/master/cmake/configs).



##  启动驱动程序
在系统启动期间，必须告知系统启动雷达的驱动程序。

将以下行添加到SD卡上的 \[extras.txt\]\(advanced-system-startup.md\) file located on your SD card.

```
ulanding_radar start /dev/serial_port
```

在上面的命令中，用连接硬件的串行端口替换最后一个参数。

如果没有指定任何端口，驱动程序将使用 /dev/ttyS2 ，即Pixhawk上的TELEM2端口。
**警告**

如果将雷达设备连接到TELEM2，请确保将参数SYS_COMPANION设置为0.否则串行端口将被另一个应用程序占用，将发生不可预测的行为。

