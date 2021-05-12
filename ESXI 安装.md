# ESXI

###说起ESXI就想到了sphere，说起sphere就想到了那片天空，讲到了天空就不得不提起德国，下半年·中德合拍·开花

## 下载镜像

直接官网注册下载，有60天的使用许可

https://my.vmware.com/group/vmware/evalcenter?p=vsphere-eval-7

##### 建议下载6.7以前的版本，根据国内外大佬所述，7.0版本移除了对 REALTEK 瑞昱网卡（蓝色的螃蟹图标）的支持，安装时会报错 No Network Adapters

https://www.xzccc.com/blog/wangluocunchu/85.html

https://www.reddit.com/r/vmware/comments/igkd62/how_to_make_a_bootable_esxi_7_stick_with_network/



笔者安装使用的6.7镜像，网卡是Realtek PCIe GBE Family Controller，主板自带的螃蟹网卡。网卡版本可进入PE，在 此电脑》属性》设备管理器 中查看

如果拥有独立网卡，或Intel网卡，装7.0版本那应该没有问题。如有问题，请见 打包驱动 章节。



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

如果报错 No Network Adapters，那就需要进行一下内容了，成功则跳过即可。

由于笔者使用6.7版本的镜像，方法一显然失败了。不过方法一胜在简单，低版本的镜像使用还是挺好的

### 方法一

#### 安装软件

适用于6.5之前的版本（不清楚6.5能不能用，工具官网说不支持6.0版本，但亲测能用）。此软件已不再更新，如不成功，请使用方法二

使用ESXi-Customizer-v2.7.2软件

https://vibsdepot.v-front.de/tools/ESXi-Customizer-v2.7.2.exe

ESXi-Customizer下载完成后，双击打开会自动解压出来得到以下文件：


![PIC20180902_183835 (1)](https://user-images.githubusercontent.com/59044398/117930367-7b197480-b330-11eb-9e07-44d4b9e79d24.png)


后缀名为 `.cmd` 的就是启动文件，是一个脚本，默认情况下这个脚本是只能支持的win8.1，win10用户打开会报错：


![PIC20180902_144756](https://user-images.githubusercontent.com/59044398/117929607-98017800-b32f-11eb-9b46-3a2b559b20b5.png)


这个时候我们用文本编辑器编辑一下ESXi-Customizer.cmd文件

添加下图红框代码并保存

```bash
set WinVer=6.3
```

![PIC20180902_184300](https://user-images.githubusercontent.com/59044398/117929741-b9fafa80-b32f-11eb-85ef-b22d2104a523.png)

![PIC20180902_184252](https://user-images.githubusercontent.com/59044398/117929729-b798a080-b32f-11eb-8482-84b69c8978fe.png)

然后重新运行ESXi-Customizer.cmd文件

教程来源：https://6iit.com/3299

#### 寻找驱动

在此网站下载

https://vibsdepot.v-front.de/wiki/index.php/List_of_currently_available_ESXi_packages

根据两位网友的经验 [网友1](https://www.cnblogs.com/huhyoung/p/9690301.html )    [网友2](https://blog.csdn.net/JENREY/article/details/105774542 )

选择了 [net55-r8168](https://vibsdepot.v-front.de/wiki/index.php/Net55-r8168)，下载 vib格式

![捕获](https://user-images.githubusercontent.com/59044398/117930701-e6634680-b330-11eb-9680-7331de711156.PNG)


#### 打包驱动

下面的联网更新选项，不要打勾

![1564](https://user-images.githubusercontent.com/59044398/117931375-b0729200-b331-11eb-99d4-bac4962cfa9a.PNG)



### 方法二

![捕获](https://user-images.githubusercontent.com/59044398/117919094-fa05b180-b31e-11eb-9f19-b2a6279f1d00.PNG)



![捕获2](https://user-images.githubusercontent.com/59044398/117919104-fe31cf00-b31e-11eb-9792-1749ef6b2f0b.PNG)



![捕获3](https://user-images.githubusercontent.com/59044398/117919108-00942900-b31f-11eb-822e-ab69012a7739.PNG)





![捕获4](https://user-images.githubusercontent.com/59044398/117919119-0427b000-b31f-11eb-9810-744d951e4e24.PNG)



![捕获444](https://user-images.githubusercontent.com/59044398/117919129-0722a080-b31f-11eb-8d49-63f368633f70.PNG)











