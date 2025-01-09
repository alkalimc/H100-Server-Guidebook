软件环境:
* OS: `Ubuntu 22.04.5 LTS x86_64`
* Kernel: `5.15.0-127-generic`
* GPU Driver: `550.127.08`
* CUDA: `12.4.1`
* CUDNN: `9.6.0`
* Anaconda: `2024.10`

硬件资源:
* CPU: `Intel Xeon Gold 5418Y (96) @ 3.800GHz`
* Memory: `DDR5-4800 RDIMM 384GB`
* GPU: `NVIDIA GeForce RTX 4090`\**3 + `NVIDIA H100 80GB HBM3`\**1
* Storage: `480GB SATA SSD` + `10TB SATA HDD`

操作:
* 使用命令`nvidia-smi`命令查询GPU的工作状态
* 使用命令`free`查看内存的占用状态
* 使用命令`squeue`查看slurm系统中任务的排队情况
* 使用命令`sinfo`查看slurm Cluster的工作状态
* 使用命令`scontrol show nodes`查看slurm Node的配置

若要显式指定任务在特定类型GPU上运行，参见[slurm系统的使用](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/slurm.md)

下一节-[部署zsh并为其安装插件](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/zsh.md)