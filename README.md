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



A. 在 https://nodejs.org/zh-cn/ 网站上下载长期维护版并安装。


B. 在Windows10本地的CMD命令行中中安装wstunnel命令：

npm install -g wstunnel


C. 远程登录Railway云的命令：

如果提示输入密码验证，密码为 uncleluo

请在自己电脑上或者网络中放行7001端口，一般本地Windows主机端口并无设限，公司网络难说！

1. 在Windows10的CMD命令行中配置连接进程命令

wstunnel -t 7001:127.0.0.1:22 wss://你在火车头网站部署好的域名 &

例子：wstunnel -t 7001:127.0.0.1:22 --proxy http://127.0.0.1:1080 wss://huoche.up.railway.app &

注意：--proxy http://127.0.0.1:1080 是代理服务器地址和端口号，Railway云禁用了很多大陆地区的IP地址，所以需要代理才能访问，如果你原生网络可以正常访问Railway云网站，则无需添加这行命令，okteto云就不用加这个了。

这里wss://后面是你自己自定义后的域名，不要忘记&符号前面有个空格，我这里以huoche为域名开头，你可以替换为你自己的。

2. 用Windows10中的PowerShell远程登录Railway云VPS命令：

ssh root@127.0.0.1 -p 7001

3. 安装VNCserver：
apt install tightvncserver

4. 安装nano编辑器
apt install nano

5. 进入 /usr/bin文件夹进行修改文件名伪装
cd /usr/bin

6. 修改文件名
mv tightvncserver daserver
mv Xtightvnc da

7. 用nano编辑器替换Xtightvnc为da
nano daserver
contorl+\ 快捷键 可以搜索替换 ，查找替换所以的Xtightvnc为da
control+o 保存

8. 设置vnc客户端登陆密码：
daserver :2000

9. 关闭vnc服务：
daserver -kill :2000

10.安装图形界面Lxde
apt install lxde

11.启用vnc服务：
daserver :2000

13. 开本地第二个PowerShell窗口：
ssh root@127.0.0.1 -p 7001 -L 5845:127.0.0.1:7900

14. VNCviewer访问：127.0.0.1:5845

15.看CPU状态命令：
apt install mate-system-monitor
mate-system-monitor
