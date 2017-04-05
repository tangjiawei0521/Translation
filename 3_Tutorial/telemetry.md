# 遥测
官网英文原文地址：https://dev.px4.io/telemetry.html

遥测可用于与QGroundControl进行通信，特别适用于调节参数，例如可以在不插入电缆的情况下更改参数。
## 3DR 无线遥测
使用3DR 无线遥测，只需要一个发射器（如果您的计算机/平板电脑上有一个WIFI卡/棒）。只需将该模块连接到TELEM端口，就可以作为一个WIFI站。
```sh
essid: APM_PIX
password: 12345678
```
一旦连接到WIFI，它应该自动连接到QGroundControl。
![wifi1](../pictures//hardware/3dr_wifi_1.JPG)
![wifi2](../pictures//hardware/3dr_wifi_2.png)
