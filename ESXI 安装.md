# ESXI

###说起ESXI就想到了sphere，说起sphere就想到了那片天空，讲到了天空就不得不提起德国，下半年·中德合拍·开花

## 下载镜像

直接官网注册下载，有60天的使用许可

https://my.vmware.com/group/vmware/evalcenter?p=vsphere-eval-7

##### 建议下载6.7以前的版本，根据国内外大佬所述，7.0版本移除了对 REALTEK 瑞昱网卡（蓝色的螃蟹图标）的支持，安装时会报错 No Network Adapters

笔者安装使用的网卡是Realtek PCIe GBE Family Controller，主板自带的螃蟹网卡。可进入PE，在 此电脑》属性》设备管理器 中查看

如果拥有独立网卡，或Intel网卡，装7.0版本那应该没有问题。如有问题，请见 打包驱动 章节。

https://www.xzccc.com/blog/wangluocunchu/85.html

https://www.reddit.com/r/vmware/comments/igkd62/how_to_make_a_bootable_esxi_7_stick_with_network/

![1070034-20180922144921273-1253551996](https://user-images.githubusercontent.com/59044398/117921417-481cb400-b323-11eb-951b-4cb10d9e16c2.png)




## 刻录镜像

使用Rufus对U盘进行刻录 

![捕获44](https://user-images.githubusercontent.com/59044398/117921515-6edaea80-b323-11eb-96f6-cdde54aff37e.PNG)


询问更新 一定要点 否 不然会出问题

![156](https://user-images.githubusercontent.com/59044398/117921743-d729cc00-b323-11eb-9d28-714657e67075.PNG)


会删除全部数据 点击是

![56+](https://user-images.githubusercontent.com/59044398/117921746-dabd5300-b323-11eb-87a5-8185bd6fce64.PNG)


完成后，把U盘插上要安装的电脑，启动。

## 打包驱动







![捕获](https://user-images.githubusercontent.com/59044398/117919094-fa05b180-b31e-11eb-9f19-b2a6279f1d00.PNG)



![捕获2](https://user-images.githubusercontent.com/59044398/117919104-fe31cf00-b31e-11eb-9792-1749ef6b2f0b.PNG)



![捕获3](https://user-images.githubusercontent.com/59044398/117919108-00942900-b31f-11eb-822e-ab69012a7739.PNG)





![捕获4](https://user-images.githubusercontent.com/59044398/117919119-0427b000-b31f-11eb-9810-744d951e4e24.PNG)



![捕获444](https://user-images.githubusercontent.com/59044398/117919129-0722a080-b31f-11eb-8d49-63f368633f70.PNG)











