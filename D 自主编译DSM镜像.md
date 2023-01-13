# ESXI

前言, AMD CPU无法使用群晖套件 VMM 虚拟机程序, 群晖不支持AMD-V技术, 如有需要请选购支持 VT-D 的英特尔CPU

### 方法一：(未成功)

网上在线编译, 由于未成功不多赘述了, 感兴趣自己尝试

(这个方法启动页面不会显示IP成功获取提示, 群晖助手也搜不到, 也不知道开机是否成功, 不知道那一步没做对反正就是不行)

项目地址: https://github.com/wjz304/Redpill_CustomBuild

转跳编译: https://wjz304.github.io/Redpill_CustomBuild/Issues.html

参考: https://wjz304.github.io/Redpill_CustomBuild/Issues.html


### 方法二：

通过Redpill镜像在ESXI完成编译并启动

(不知道这俩个有什么不同，笔者选择的是flat)

    访问并下载ESXI的镜像
    https://github.com/fbelavenuto/arpl/releases/tag/v1.0-beta9   
    
![捕获3](https://user-images.githubusercontent.com/59044398/211724125-df18c734-bdfe-4ede-bdcd-00f35e384294.PNG)

#### 配置
 
![image](https://user-images.githubusercontent.com/59044398/211724504-e6148a1b-326a-4eeb-b4c1-9dd704b467ad.png)

![image](https://user-images.githubusercontent.com/59044398/211724838-84b27c1a-ee2b-425c-92af-37ce60a1fac8.png)

所有硬盘都要设为sata 控制器，启动引导用Bios 

![image](https://user-images.githubusercontent.com/59044398/211725170-8aae0f84-357f-44ba-b1d5-67113bbea24a.png)
    
想要万兆网络可以用 VMXNET3，镜像已内置驱动    
    
![image](https://user-images.githubusercontent.com/59044398/211724572-2872a690-a4b5-4036-9e84-963e75469165.png)
   
#### 开机

点击开机,首先配置洗白用的MAC Address(没有可以跳过,现在中国地区不用中国特供群晖账号也用不了QuickConnect了)
 


![image](https://user-images.githubusercontent.com/59044398/212305844-23e12c5f-210c-4384-adaa-c5eee386b705.png)

 
![image](https://user-images.githubusercontent.com/59044398/212305727-70c963a2-af6f-4432-afb1-70abf0053c62.png)
    
配置好后页面会卡住,直接关机
    
![image](https://user-images.githubusercontent.com/59044398/212307166-50ed8d4f-619e-467f-9450-88e63d1604e2.png)

为了使用链路聚合建议添加两个网卡,MAC改为手动设置

不能设置的要去vSwitch 更改设置,允许 MAC 更改

![image](https://user-images.githubusercontent.com/59044398/212307489-dcf9c007-57d0-4b4a-a24a-7b79c6b45a60.png)


#### 开始编译

m. 再次开机,选择编译机型

![image](https://user-images.githubusercontent.com/59044398/212332940-977629e4-9c07-4718-83d2-44d45ea050ed.png)

![image](https://user-images.githubusercontent.com/59044398/212333082-927f4923-121e-436a-a719-b6e62757e631.png)

n. 选择系统版本,因为DS3617xs只支持DSM7.0,

![image](https://user-images.githubusercontent.com/59044398/212333200-9eb6474d-ba11-4fc2-a153-5a7ed5df166d.png)

最上面最新的是DSM7.1.1,中间是7.1.0,下面是7.0.1

![image](https://user-images.githubusercontent.com/59044398/212333427-8f310b02-a2b7-46e2-9920-e0fa61f5234e.png)

s. 输入SN码洗白,如果你有,不填是默认自动生成

![image](https://user-images.githubusercontent.com/59044398/212333924-7449fa95-bd81-4244-8ccb-98a79e86d619.png)

a. Addons是添加核显驱动,由于笔者使用的是EPYC 霄龙,没有核显跳过
 
x. 这里可以查看 SATA 端口,对于ESXI安装没有影响,可以随便看看

![image](https://user-images.githubusercontent.com/59044398/212334357-b521ecc2-a819-4027-a7a8-4bf9bfcf82e1.png)

![image](https://user-images.githubusercontent.com/59044398/212335200-893df76b-03cf-4b7d-b609-519c2cf102e0.png)

![image](https://user-images.githubusercontent.com/59044398/212335547-c324a1eb-3bab-4156-97c9-d256c4738a47.png)

d. 全部设置完成, Bulid the loader 开始编译

![image](https://user-images.githubusercontent.com/59044398/212335843-de672bf5-2fcd-446a-aec0-cd650a1ecaea.png)

![image](https://user-images.githubusercontent.com/59044398/212335996-260d405c-b91b-41bb-8b55-5ce4508f58ca.png)

等待编译完成会自动跳转,回车 Boot the loader 开机

![image](https://user-images.githubusercontent.com/59044398/212336130-3d068b11-ffa8-4cd3-9572-dd47376d13be.png)

成功开机,自动获取IP

(这里用路由器DHCP手动指定IP有可能会造成群晖开机失败,显示无法连接,建议在群晖系统内指定IP)

![image](https://user-images.githubusercontent.com/59044398/212336378-e55a77f7-7db1-4980-985a-063cadb9b5de.png)




