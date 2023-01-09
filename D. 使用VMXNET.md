# ESXI

Windows 配置 VMXNET 发现无法联网

原因是没有在虚拟机内安装 VMware Tool


![image](https://user-images.githubusercontent.com/59044398/211275310-e2b11ab2-4128-4150-8ebb-62fe0518dff6.png)


### 1 点击安装VMware Tool，系统里会挂载一个虚拟磁盘

![image](https://user-images.githubusercontent.com/59044398/211275517-0b1ddafc-e38a-4b2e-833b-c2c2a0f126ab.png)

双击或右键打开，按正常流程安装即可

安装完成后就会自动连接 VMXNET 了

![image](https://user-images.githubusercontent.com/59044398/211275735-8144c127-623d-472b-b567-52a28c02b3bf.png)


### 2 传输测试

#### local Sata disk to NAS Sata

![image](https://user-images.githubusercontent.com/59044398/211276340-eefe9d3d-68fa-4d2f-a758-fdd4241ca960.png)

#### NAS Sata disk to local Sata (不清楚为什么到local的操作那么慢，尝试给磁盘更换Nvme控制器，无用)

![image](https://user-images.githubusercontent.com/59044398/211277014-ef903943-2307-4df0-9eaa-a6fedc4cec36.png)


#### NAS Sata to NAS Sata Raid 6

![image](https://user-images.githubusercontent.com/59044398/211277398-4ff1471b-7c22-463a-9f14-3836d56626bb.png)

#### NAS Sata Raid 6 to NAS Sata

![image](https://user-images.githubusercontent.com/59044398/211277532-ff3f8732-029b-431f-98da-adad059264f5.png)


