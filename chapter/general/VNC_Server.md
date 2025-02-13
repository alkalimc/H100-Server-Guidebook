操作:
* 使用命令`vncserver`初始化VNC
* 使用命令`vncserver -kill :*`关闭VNC桌面
* 使用命令`touch ~/.vnc/config & echo -e "geometry=1920x1080\nlocalhost=no" >> ~/.vnc/config`配置VNC
* 使用命令`cat /etc/tigervnc/vncserver.users`查看分配的端口信息