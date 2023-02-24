# ESXI

1：1 完全复制的DSM虚拟机无法打开，DHCP获取IP失败

### 解决方法

网卡要和原来的设置一样，改为手动设置可更改

MAC地址，数量，原来创造引导时添加了多少个MAC就要添加多少个网卡

少了添加会造成局域网找不到IP。

如果create的时候是ESXI自动分配MAC，那就无法修改为和原来一样的了，会显示报错<此地址为ESXI预留>

![image](https://user-images.githubusercontent.com/59044398/221155473-947c6e0b-225b-4f2d-8bb9-633f9140ff12.png)
