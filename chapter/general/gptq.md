环境部署:
* 使用命令`conda create -n auto-gptq python=3.12.7`部署虚拟环境
* 使用命令`conda activate auto-gptq`激活虚拟环境
* 使用命令`pip config set global.index-url https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple`使用镜像源
* 使用命令`conda install pytorch torchvision torchaudio pytorch-cuda=12.4 -c pytorch -c nvidia`部署`PyTorch`环境
* 使用命令`cd /data/disk0/Models/AutoGPTQ`进入`AutoGPTQ`目录
* 使用命令`pip install -vvv --no-build-isolation -e .`部署`AutoGPTQ`环境
* 使用命令`pip install autoawq`部署`AutoAWQ`环境