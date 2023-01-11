# ESXI


### 方法一：


### 方法二：

通过Redpill镜像在ESXI完成编译并启动

(不知道这俩个有什么不同，笔者选择的是flat)

    访问并下载ESXI的镜像
    https://github.com/fbelavenuto/arpl/releases/tag/v1.0-beta9   
    
![捕获3](https://user-images.githubusercontent.com/59044398/211724125-df18c734-bdfe-4ede-bdcd-00f35e384294.PNG)


 
![image](https://user-images.githubusercontent.com/59044398/211724504-e6148a1b-326a-4eeb-b4c1-9dd704b467ad.png)

![image](https://user-images.githubusercontent.com/59044398/211724838-84b27c1a-ee2b-425c-92af-37ce60a1fac8.png)

所有硬盘都要设为sata 控制器，启动引导用Bios 

![image](https://user-images.githubusercontent.com/59044398/211725170-8aae0f84-357f-44ba-b1d5-67113bbea24a.png)


    
想要万兆网络可以用 VMXNET3，镜像已内置驱动    
    
![image](https://user-images.githubusercontent.com/59044398/211724572-2872a690-a4b5-4036-9e84-963e75469165.png)
   
    
    
    
    
    
    
