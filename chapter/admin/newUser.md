新建用户:
其中`username`应替换为实际用户名
* 使用命令`sudo useradd -m username -s /bin/bash`新建用户并指定shell为bash，
* 使用命令`sudo passwd username`为新用户设置密钥

部署zsh和Anaconda环境
> 管理员应避免直接在自己账号的ssh连接内通过`su example`切换到其他用户为其配置环境或排障，此举会临时继承自己环境中定义的环境变量到其他用户的环境中，导致出现未定义的问题

当管理员为新用户部署环境时，应当直接使用为该用户设置的凭证连接服务器，参见[部署ZSH并为其安装插件](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/zsh.md)及[Anaconda环境的部署与使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/anaconda.md)

下一节-[firewall的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/admin/firewall.md)