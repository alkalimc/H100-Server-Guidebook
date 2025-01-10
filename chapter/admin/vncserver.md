> 为需要桌面环境的用户开启vnc服务  
> Remote Display System: TigerVNC  
> 桌面环境：Xfce 4.16  

操作：
* 在该用户终端下使用命令`vncserver`新建`~/.vnc`文件夹并配置VNC密码
* 在该用户终端下使用命令`vncserver -kill :*`关闭刚启动的VNC桌面
* 在该用户终端下使用命令`touch ~/.vnc/config & echo -e "geometry=1920x1080\nlocalhost=no" >> ~/.vnc/config`配置VNC桌面环境
* 使用命令`cat /etc/tigervnc/vncserver.users`查看已分配的端口信息
* 使用命令`sudo vim /etc/tigervnc/vncserver.users`为用户配置端口信息，在文件最后添加`:port=username`，其中`port`为VNC使用的端口，`username`为该用户的用户名
* 使用命令`sudo systemctl start tigervncserver@:port`为该用户开启VNC服务，其中`port`为刚配置的VNC端口
* 使用命令`sudo netstat -tunlp | grep vnc`查看端口使用信息
* 使用命令`journalctl -xeu tigervncserver@:port`查看启动信息，其中`port`为刚配置的VNC端口
* 使用命令`sudo enable tigervncserver@:port`设置为开机启动，其中`port`为刚配置的VNC端口
* 如有需要，参照 [fail2ban的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/admin/fail2ban.md) 为开启的VNC服务开放防火墙端口，真正使用的端口号为该用户文件目录下`~/.vnc/*.pid`文件的文件名最后几位数字