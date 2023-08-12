# ESXI

#### 据说此方法英特尔可行，AMD不行
```
运行了解锁脚本后，安装镜像 macOS.Catalina.iso 一直卡在苹果图标，没有进度条。
```
#### 方法一

1. 把一下压缩包用网页上传直至ESXI任意储存空间
  
   [esxi-unlocker-master.tar.gz](https://github.com/Meidouzanget/ESXI/files/12326313/esxi-unlocker-master.tar.gz)

2. SSH 登录esxi，选择上传的储存空间
  ```
  cd vmfs/volumes
  ls
  cd 选出你上传的地方
  ```
  ![image](https://github.com/Meidouzanget/ESXI/assets/59044398/986f1263-fea8-4ac2-8cfd-53d7106a5312)

3. 解压压缩包
  ```
  tar xzvf esxi-unlocker-master
  ls 刷新一下
  ```

4. 进入解压出来的文件夹并运行安装脚本
  ```
  cd esxi-unlocker-master
  ./esxi-install.sh
  运行测试看安装是否曾成功
  ./esxi-smctest.sh
  ```
  ![image](https://github.com/Meidouzanget/ESXI/assets/59044398/1a80e0db-dbe5-4a08-8d0f-233dd678c786)

5. 重启ESXI，然后进行镜像安装虚拟机的常规常规操作


#### 方法二
to be continue
```
https://www.geekrar.com/install-macos-catalina-on-vmware-on-amd-systems/
```

















