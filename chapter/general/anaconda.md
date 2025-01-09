> 管理员应避免直接在自己账号的ssh连接内通过`su example`切换到其他用户为其配置环境或排障，此举会临时继承自己环境中定义的环境变量到其他用户的环境中，导致出现未定义的问题

> 如果需要使用zsh，应在执行此节操作前完成[部署zsh并为其安装插件](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/zsh.md)，否则需要手动添加conda环境变量到`.zshrc`

安装步骤:
* 使用命令`/data/disk0/Tutorial/Anaconda3-2024.10-1-Linux-x86_64.sh`启动部署程序，不得在此处使用`sudo`
* 当出现`Please, press ENTER to continue`，一直按下Enter直至出现`Please answer 'yes' or 'no':'`，输入`yes`
* 检查`[/home/example/anaconda3] >>>`中`example`的内容是否为你的用户名，如果是则按下Enter
* 当出现`You can undo this by running ``conda init --reverse $SHELL``? [yes|no]`，输入`yes`
* 出现`Thank you for installing Anaconda3!`即意味着Anaconda现已被成功部署到你的环境中，重连ssh即可使用

使用教程:
下文中`example`应替换为虚拟环境的名称，`package`应替换为虚拟环境内的包名

* 使用命令`conda config --set custom_channels.auto https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/`来使conda使用TUNA镜像
* 使用命令`conda env list`查看当前用户下conda内的所有虚拟环境
* 使用命令`conda list`查看当前虚拟环境下conda安装的所有包
* 使用命令`conda create -n example python=version`创建新的虚拟环境，其中`version`应被替换为虚拟环境内使用的python版本，如果不需要指定python版本可以使用`conda create -n example`
* 使用命令`conda activate example`激活虚拟环境
* 使用命令`conda install package`安装包
* 使用命令`deactivate`退出虚拟环境
* 使用命令`conda remove -n example package`删除虚拟环境内的指定包
* 使用命令`conda remove -n example --all`删除虚拟环境
* 使用命令`conda update conda`更新conda

安装PyTorch: `conda install pytorch torchvision torchaudio pytorch-cuda=12.4 -c pytorch -c nvidia`

下一节-[HuggingFace模型及数据集的下载的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/huggingface.md)