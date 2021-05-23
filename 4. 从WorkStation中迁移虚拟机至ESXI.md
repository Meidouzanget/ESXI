# ESXI

## 从WorkStation中迁移虚拟机

##### 首先这是一个失败的过程记录

笔者并不建议这么做，因为会经历一系列的问题

依顺序会经历一下流程：导入失败，无法开机，无法修改配置，开机蓝屏，镜像修复，漫长等待，修复失败

笔者实在没精力花几个小时逐个方法尝试导入了，毕竟重装系统加软件也不过一个小时的工作

##### 如果你有成功的方法，不妨我联系



### 基本方法：

1、先在Vmware workstation工作站上导出虚拟机为vof文件

导出前，要先关闭虚拟机，然后右键–》文件–》导出为OVF(E)…
![1219693-20210105211811658-1902715140](https://user-images.githubusercontent.com/59044398/117949801-13b9ef80-b345-11eb-8721-f2f305220cc5.png)

导出完成后，得到4个文件，如下图所示，其中红色圈起的是需要用到的文件

![1219693-20210105211824028-640613749](https://user-images.githubusercontent.com/59044398/117949869-27fdec80-b345-11eb-90c5-bc2a217630d4.png)



2、打开exsi管理web后台，需要上传两个文件,扩展名为ovf和vmdk的文件,然后下图操作即可,最后启动电源开机。

![1219693-20210105211837679-1294290014](https://user-images.githubusercontent.com/59044398/117949892-2f24fa80-b345-11eb-87b8-d84b25b4621c.png)

![1219693-20210105211848964-28389955](https://user-images.githubusercontent.com/59044398/117949921-36e49f00-b345-11eb-991b-8284aea9fac3.png)

![1219693-20210105211859793-167518269](https://user-images.githubusercontent.com/59044398/117949929-39df8f80-b345-11eb-9363-23c9f52860fa.png)

![1219693-20210105211914991-1019638791](https://user-images.githubusercontent.com/59044398/117949940-3cda8000-b345-11eb-8dd9-0b01fb43ed34.png)

![1219693-20210105211928268-1648511727](https://user-images.githubusercontent.com/59044398/117949950-3f3cda00-b345-11eb-8db1-e8b3cfb1de4f.png)

### 问题

#### 导入失败

因为导出的配置文件的版本太高

笔者所用WorkStation15，ESXI6.7

需要修改 Windows 10 x64.ovf 文件，右键用EditPlus打开

把原本<vssd:VirtualSystemType>vmx-16</vssd:VirtualSystemType>

改为vmx-14,即可成功导入

![捕获7891](https://user-images.githubusercontent.com/59044398/117951579-e1a98d00-b346-11eb-8cff-a0ae8d8909c5.PNG)



#### 打开与改修虚拟机失败

重启ESXI即可



#### 打开蓝屏

![1586](https://user-images.githubusercontent.com/59044398/117955116-46b2b200-b34a-11eb-9347-42f1b5bb3154.PNG)



#### 镜像修复

导入镜像

![41548654](https://user-images.githubusercontent.com/59044398/117955060-3995c300-b34a-11eb-8126-49d50a6bf6ea.PNG)



启动，按ESC
![1586](https://user-images.githubusercontent.com/59044398/117953774-f1c26c00-b348-11eb-97dd-a14b4fe3645c.PNG)



选第三个回车，然后一直按任意键

![156456](https://user-images.githubusercontent.com/59044398/117953830-0141b500-b349-11eb-9ca2-10dafcb8e928.PNG)



安装界面选择修复系统

![569+8](https://user-images.githubusercontent.com/59044398/117954004-2d5d3600-b349-11eb-9669-076ce3975b4d.PNG)




进入疑难解答，高级选项，启动修复：失败

系统映像恢复，盘立没有映像。插U盘直通或许可行，没去试

![56569](https://user-images.githubusercontent.com/59044398/117954179-58e02080-b349-11eb-8786-ac3ad08d189f.PNG)



使用设备：没法进去，点击就是重启

![4158475](https://user-images.githubusercontent.com/59044398/117954715-df94fd80-b349-11eb-84bd-b191918bb1de.PNG)


![154544545](https://user-images.githubusercontent.com/59044398/117954738-e6bc0b80-b349-11eb-8bc1-10dab9cf210b.PNG)





























