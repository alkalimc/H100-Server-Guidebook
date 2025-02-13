huggingface-cli的使用:
* 使用命令`huggingface-cli download --resume-download owner/model --local-dir /data/disk0/Models/model`下载模型，其中`owner/model`应替换为模型名称
* 使用命令`huggingface-cli download --repo-type dataset --resume-download dataset --local-dir /data/disk0/Dataset/dataset`下载训练集，其中`dataset`应替换为训练集名称

hfd的使用:
* 使用命令`source /etc/profile`使`hfd`生效
* 使用命令`cd /data/disk0/Models`或命令`cd /data/disk0/Dataset`进入存储模型或训练集的目录
* 使用命令`hfd.sh model`下载模型，其中`model`应替换为模型名称
* 使用命令`hfd.sh dataset --dataset`下载训练集，其中`dataset`应替换为训练集名称

需要使用token的下载:
下文中`hf_***`应替换为实际Hugging Face的Access Token
* 使用命令`huggingface-cli download --token hf_*** --resume-download owner/model --local-dir /data/disk0/Models/model`下载模型，其中`owner/model`应替换为模型名称
* 使用命令`hfd.sh owner/model --hf_username YOUR_HF_USERNAME --hf_token hf_***`下载模型，其中`YOUR_HF_USERNAME`应替换为Hugging Face的用户名，`owner/model`应替换为模型名称

权限处理:
* 使用命令`chmod -R 777 /data/disk0/Models/model`处理模型权限，其中`model`应替换为模型名称
* 使用命令`chmod -R 777 /data/disk0/Dataset/dataset`处理训练集权限，其中`dataset`应替换为训练集名称

下一节-[SLURM系统的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/slurm.md)