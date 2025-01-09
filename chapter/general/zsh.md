此节为可选节，对于没有zsh使用需求的用户，可以跳过此节并保持使用bash

部署oh-my-zsh:
* 使用命令`/data/disk0/Tutorial/zsh/install.sh`启动部署程序，不得在此处使用`sudo`
* 当出现`Do you want to change your default shell to zsh? [Y/n]`，输入`Y`
* 当出现`Password:`，输入你的密钥

安装插件:
此节为可选节，对于没有zsh插件使用需求的用户，可以跳过此节

* 使用命令`git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`安装语法高亮插件
* 使用命令`git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions`安装历史记录补全插件

安装主题:
此节为可选节，对于没有zsh更换主题需求的用户，可以跳过此节

* 使用命令`cp -r /data/disk0/Tutorial/zsh/powerlevel10k ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k`

修改配置文件:

* 使用命令`nano ~/.zshrc`
* 转到文件尾部，另起一行添加`setopt no_nomatch`
* 如果安装了历史记录补全插件，可以另起一行添加`export ZSH_AUTOSUGGEST_STRATEGY=(history completion)`以启用标准补全功能
* 如果安装了任意插件，找到行`plugins=(git)`并在括号内选择`zsh-syntax-highlighting`或（和）`zsh-autosuggestions`间隔空格后填入
* 如果安装了主题，找到行`ZSH_THEME="robbyrussell"`将其改为`ZSH_THEME="powerlevel10k/powerlevel10k"`
* 使用命令`source .zshrc`
* 对于安装了主题的用户，请按照终端提示完成主题设定


下一节-[Anaconda环境的部署与使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/anaconda.md)