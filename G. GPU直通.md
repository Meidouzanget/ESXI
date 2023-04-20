# ESXI

要实现直通GPU能成功调用，分为ESXI设置的部分和Windows设置的部分

### ESXI设置

#### 在 管理--->硬件 中找到对应的显卡，点击切换直通
![image](https://user-images.githubusercontent.com/59044398/233246550-7d49d7f2-0724-4f40-9973-1f65215edfa8.png)

#### 选择虚拟机，添加PEI设备
如果提示不能添加，则需要关闭[虚拟机选项]里的VBS（基于虚拟化的安全性），和关闭CPU选项下面的所有“向客户机操作系统公开硬件辅助的虚拟化”
![image](https://user-images.githubusercontent.com/59044398/233247037-b87ea43a-e592-4dc7-9acb-e5b1af20ce25.png)

#### 预留全部内存，不然会开机报错
![image](https://user-images.githubusercontent.com/59044398/233248116-0920842e-311c-4104-907f-e1035d8da6a5.png)

#### 打开虚拟机的电源，如果开机报错：模块“DevicePowerOn”打开电源失败。

确认虚拟机是否EFI引导：编辑虚拟机 – 虚拟机选项 – 引导选项 – 固件 – EFI
![image](https://user-images.githubusercontent.com/59044398/233249115-9fc180de-4cbc-4f53-a9e5-b38086daecb2.png)

##### 点击虚拟机选项，打开高级

配置参数---> 添加参数，添加以下两项
```
pciPassthru.use64bitMMIO=”TRUE”
pciPassthru.64bitMMIOSizeGB=64
```
![image](https://user-images.githubusercontent.com/59044398/233247188-c2577a7c-c126-49ce-a583-b058e2ee26bb.png)
![image](https://user-images.githubusercontent.com/59044398/233247965-0f7ee717-f8dd-4cdc-99f3-924ab88f493b.png)

#### 在Windows打开设备管理器，看到这里有GPU就是添加成功了。
但是任务管理器还是没有显示GPU，接下来我们要进行Windows的设置
![image](https://user-images.githubusercontent.com/59044398/233249523-b2a4219d-16c6-48ba-b963-2da7d3b1d4a3.png)


### Windows设置








