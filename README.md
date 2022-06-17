1. 进入自己的GitHub账号，上传解压后的罗叔提供的4个文件，并为项目命名。

2. 获取自己关于本项目的git链接待用。

3. 进入已经登录的okteto云填入自己项目的git链接并部署。

--------------------------提前准备---------------------------------
💪⛳由于老罗的视频都有着承上启下的连续性，所以在您自己的Linux VPS上或者linux本地系统上的操作如下，具体可以参考前期的火车头的视频有介绍：

视频地址：https://youtu.be/AlVukFya7AM

A. 在Linux VPS的Terminal上安装配置命令：

1. 安装npm命令：

apt install npm

2. 安装wstunnel命令：

sudo npm install -g wstunnel
--------------------------提前准备----------------------------------

4. 项目安装成功后本地终端进行配置：

wstunnel -t 3333:127.0.0.1:22 wss://你在okteto上新建项目的网址/ &

例子：wstunnel -t 3333:127.0.0.1:22 wss://areyouok-uncleluo.cloud.okteto.net/ &

5. 本地终端继续ssh获取管理员root权限：

ssh root@127.0.0.1 -p 3333
6. 安装VNC：

apt install tightvncserver

7. 安装Linux桌面：

apt install lxde

8．配置VNC远程登录密码：

vncserver :1

9. 保持第一个终端状态不变，不要关闭第一个终端窗口，开第二个终端窗口并输入：

wstunnel -t 5806:127.0.0.1:5901 wss://你在okteto云上的项目网址/ &

例子：wstunnel -t 5806:127.0.0.1:5901 wss://areyouok-uncleluo.cloud.okteto.net/ &

10. 本地VNC Viewer客户端登录：

127.0.0.1:5806
