操作:
其中`port`应被替换为要开放的VNC端口
* 使用命令`sudo vim /etc/tigervnc/vncserver.users`为用户配置端口信息，在文件最后添加`:port=username`，`username`应被替换为用户名
* 使用命令`sudo systemctl start tigervncserver@:port`为该用户开启VNC服务
* 使用命令`sudo netstat -tunlp | grep vnc`查看端口使用信息
* 使用命令`journalctl -xeu tigervncserver@:port`查看服务状态
* 使用命令`sudo enable tigervncserver@:port`将服务链接到开机启动
* 参照[fail2ban的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/admin/fail2ban.md)开放防火墙端口，实际使用的端口号为目标用户文件目录下`~/.vnc/*.pid`文件文件名的最后几位数字