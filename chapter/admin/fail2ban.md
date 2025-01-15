> fail2ban用于保护服务器免遭自动化工具对其密钥的爆破
> 因多次错误提交密钥而被误封请联系管理员或等待1h再次尝试与服务器建立连接

安全策略:
* 时段: `1min`
* 错误尝试次数: `5`
* 封禁时间: `1h`
* 封禁端口: `all`

操作:
* 使用命令`sudo nano /etc/fail2ban/jail.local`编辑安全策略
* 使用命令`sudo systemctl restart fail2ban`重启fail2ban服务
* 使用命令`sudo fail2ban-client status sshd`查看封禁列表
* 使用命令`sudo fail2ban-client set sshd unbanip ip`解封IP地址，其中`ip`应被替换为实际IP地址

下一节-[vncserver的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/admin/vncserver.md)