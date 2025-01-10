# yuhaolab-H100服务器使用手册
> 获取用户账号、申请电源操作、更换环境组件应在群内申请
> 其他高权限操作的申请应联系微信群内的管理员

本手册用于指导用户访问服务器、部署环境及提交计算负载，在使用服务器之前，应注意以下操作规范:

* 不得在服务器上部署**任何**未经授权的允许在内网外连接服务器的服务，包括但不限于frp服务和支持内网外访问的远程桌面服务
* 不得进行未经授权的网络操作，包括但不限于开放或关闭端口，修改网卡配置，重启网络服务等
* 避免使用`sudo`功能，如果无法避免，请在使用前确认命令的执行对象，一般不得在root用户下部署任何环境
* 所有密钥必须足够复杂以避免安全性问题，不得使用安全欠佳的终端设备与服务器建立连接
* 未经特殊说明服务器内的一切数据禁止分发，授权分发的内容请传至终端后再进行进一步操作

注意:
* 应使用[Anaconda](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/anaconda.md)部署python环境，一般不得在服务器基础环境内安装pip包
* 应使用[SLURM](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/slurm.md)部署长时计算任务，一般不得直接在终端下部署工作负载
* 应将服务部署到`/data/disk0/Service`，已经为其创建PATH
* `/home`目录已经被连接到`/data/disk0/Home`，因此允许直接在自己的家目录下部署环境及存储资源
* 如有需求，应在`/data/disk0/Workspace`下创建其他工作目录
* 应将手动下载的模型文件存储在`/data/disk0/Models`下以便共享使用，对于有保密需求的，应将其存储在自己的家目录下
* 应将手动下载的训练集请存储在`/data/disk0/Dataset`下以便共享使用，对于有保密需求的，应将其存储在自己的家目录下
* 启用了HuggingFace镜像站的环境变量，可以通过`/data/disk0/Service/hfd.sh`调用镜像下载模型，参见[hfd工具的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/hfd.md)
* 将HuggingFace的工作目录修改到了`/data/disk0/HuggingFace`下
* 一般应避免使用`rm -rf`，以`mv`要删除的文件到`/data/disk0/Trash`下替代
* 启用了fail2ban功能，因多次错误提交密钥而被误封请联系管理员或等待1h再次尝试与服务器建立连接
* 管理员应避免直接在自己账号的ssh连接内通过`su example`切换到其他用户为其配置环境或排障，此举会临时继承自己环境中定义的环境变量到其他用户的环境中，导致出现未定义的问题

### 用户应先修改管理员提供的默认密钥为自己的强密钥

快速入门手册:
* [服务器软硬件](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/softwareAndHardware.md)
* [部署ZSH并为其安装插件](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/zsh.md)
* [Anaconda环境的部署与使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/anaconda.md)
* [Hugging Face模型及数据集的下载的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/huggingface.md)
* [SLURM系统的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/slurm.md)

管理手册:
* [新用户环境的部署](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/admin/newUser.md)
* [firewall的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/admin/firewall.md)
* [fail2ban的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/admin/fail2ban.md)
* [vncserver的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/admin/vncserver.md)

附加文件:
* [终端字体](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/file/font)