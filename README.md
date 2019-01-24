# 萌咖大佬的一键DD Win脚本

无限制全自动dd安装Windows

突破没有VNC,没有救援模式,内存比dd包小的限制.

使用Debian Live CD中的busybox做中间媒介,经过复杂的处理,

使本机的网络参数传进Windows操作系统中,

即使没有DHCP能够让Windows获取网络参数,

也能让Windows操作系统在开机的第一时间能够连通网络.


## 1.需求:
```
#Debian/Ubuntu
## 一般自带
#RedHat/CentOS
yum install glibc-common
```

## 2.限制:
需要定制dd包.

开启内置Administrator账户登录(配置自动登陆)..

开启远程桌面(默认3389端口).

禁用UAC..

适当的调整防火墙.(可选)

需要相关的虚拟化驱动.

VirtIO驱动(备份下载) XEN驱动(备份下载)

dd包解压后的体积不能超过机器第一块硬盘的最大容积.


## 3.使用方法:

``` 
wget --no-check-certificate -qO InstallNET.sh 'https://raw.githubusercontent.com/veip007/DDWIN/master/InstallNET.sh' && bash InstallNET.sh -dd '[Windows dd包直连地址]'
``` 

## 萌咖提供的demo包(1.19G;已激活):
``` 
https://moeclub.org/get-win7embx86-auto
# 谷歌文件ID: 1srhylymTjYS-Ky8uLw4R6LCWfAo1F3s7
# 该包只添加了VirtIO驱动,理论上仅能在KVM,Hyper-V构架下正常运行.
# 如需在其他虚拟化构架下运行,请自行添加相关虚拟化驱动.
``` 
使用的是Windows Embedded Standard 7(Thin PC)作为底包,官方精简.

如需其他组件,例如:完整的桌面特征,Windows照片查看器等.

请参考: Thin PC (Win7 Embedded) 安装组件


## 4.使用示例:
```
#在你的机器上全新安装,如果你有VNC,可以看到全部过程.
#在dd的过程中,会卡在分区的界面上,不会走进度条.完成后将会自动重启.
 
wget --no-check-certificate -qO InstallNET.sh 'https://raw.githubusercontent.com/veip007/DDWIN/master/InstallNET.sh' && bash InstallNET.sh -dd 'https://moeclub.org/get-win7embx86-auto'
```

备份地址脚本
```
wget --no-check-certificate -qO InstallNET.sh 'https://raw.githubusercontent.com/veip007/DDWIN/master/InstallNET.sh' && bash InstallNET.sh -dd 'https://doc-0k-08-docs.googleusercontent.com/docs/securesc/ha0ro937gcuc7l7deffksulhg5h7mbp1/fdnl53aj475j7pjp7e70dbvp445i5b2e/1548338400000/17128039988164006870/*/1FXf5FOU0J-V4TVrcAmLNDI--bhl0pLiL?e=download'
```


## 5.使用示例(指定网络参数):
```
# 将X.X.X.X替换为自己的网络参数.
# --ip-addr :IP Address/IP地址
# --ip-mask :Netmask   /子网掩码
# --ip-gate :Gateway   /网关
# wget --no-check-certificate -qO InstallNET.sh 'https://raw.githubusercontent.com/veip007/DDWIN/master/InstallNET.sh' && bash InstallNET.sh --ip-addr X.X.X.X --ip-mask X.X.X.X --ip-gate X.X.X.X -dd 'https://moeclub.org/get-win7embx86-auto'
```


## 6.注意事项:

1)远程登陆账号为: ```Administrator```

2)远程登陆密码为: ```Vicer```

3)仅修改了主机名,可放心使用.(建议自己制作.)

4)使用的公用网盘,如需长期/大量使用此包请自行备份.

5)如果因此违反了TOS,萌咖不负任何责任.


## 7.可能用到的命令:
```
::以管理员身份运行CMD::
 
::更改用户的密码
net user [用户名] [密码]
::激活 Administrator 账户
net user Administrator /active:yes
::设置 Administrator 账户密码
net user Administrator [新密码]
::添加用户
net user [用户名] [密码] /add
::将用户添加至 Administrator 组
net localgroup Administrators [用户名] /add
::删除用户
net user [用户名] /del
```

## 8.温馨提示:
在磁盘管理中,点击’C‘盘,右键选择’扩展卷‘,可以直接’增加‘C盘的空间.

激活相关请参考: https://moeclub.org/kms

## 9.萌咖提供的可用包:

与本地用iso镜像安装过程一样,如果你有VNC,可看到全部过程.

因为全新安装!!! 全新安装!!! 全新安装!!! 所以会等待久一点.

Windows Embedded 8.1 Industry Pro x64 (2.87G;KVM;XEN;Hyper-V;未激活)
```
直链:
https://moeclub.org/get-win8embx64-auto
谷歌网盘文件ID:
1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J
```
## 备份萌咖的Win7 DD包
```
https://drive.google.com/open?id=1FXf5FOU0J-V4TVrcAmLNDI--bhl0pLiL
```
转载于萌咖https://moeclub.org/2017/11/19/483/
