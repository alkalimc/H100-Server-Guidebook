操作:
* 使用命令`sudo firewall-cmd --list-ports`查看防火墙开放的所有端口
* 使用命令`sudo firewall-cmd --zone=public --add-port=port/tcp --permanent`启用端口，其中`port`应被替换为实际要启用的端口
* 使用命令`sudo firewall-cmd --zone=public --remove-port=port/tcp --permanent`禁用端口，其中`port`应被替换为实际要禁用的端口
* 使用命令`sudo firewall-cmd --reload`重启防火墙

下一节-[fail2ban的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/admin/fail2ban.md)