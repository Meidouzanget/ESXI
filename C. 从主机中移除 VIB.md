# ESXI

由于错误的删除了 DELL SupprotAssist，重新相同版本的会装不进去，只能卸载后再装

DEL_bootbank_dcism_4.3.0.0.2781-DEL.700.0.0.15843807.vib(安装完后就是dcism)

### 卸载

查看所有vib
esxcli software vib list

查看名为 dcism的vib
esxcli software vib list | grep dcism

移除名为dcism的vib
esxcli software vib remove --vibname=dcism

卸载成功
![image](https://user-images.githubusercontent.com/59044398/211201791-7fb131eb-77d2-4ba2-8709-ada3c3943490.png)

### 重新安装











