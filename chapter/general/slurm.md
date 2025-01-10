概览:
* 使用命令`squeue`查看slurm系统中任务的排队情况
* 使用命令`sinfo`查看slurm Cluster的工作状态
* 使用命令`scontrol show nodes`查看slurm Node的配置

部署计算任务:
* 使用命令`cd path`转到工作目录下，其中`path`应改为项目目录
* 使用命令`nano .slurm_job.sbatch`打开项目配置文件并在其中填写你的项目配置
* 样例配置:

```
#!/bin/bash
#SBATCH --job-name=
#SBATCH --output=%j.out
#SBATCH --error=%j.err
#SBATCH --time=24:00:00
#SBATCH --nodes=1
#SBATCH --partition=compute
#SBATCH --ntasks=1
#SBATCH --gres=

source 
conda activate 
cd 
python 
```
* 配置注释

```
#!/bin/bash
#SBATCH --job-name=example #example应改为项目名称
#SBATCH --output=%j.out
#SBATCH --error=%j.err
#SBATCH --time=24:00:00 #长时任务应按需修改
#SBATCH --nodes=1
#SBATCH --partition=compute
#SBATCH --ntasks=1 #CPU密集型负载应将此值增大，取值在1-96之间，不超过48为宜
#SBATCH --gres=H100:1 #调用n张4090其值应为4090:n，n取值在1-3之间，调用H100其值应为H100:1

source /your/conda/path/etc/profile.d/conda.sh #应改为家目录下的conda环境目录
conda activate name #name应改为项目虚拟环境名称
cd /your/own/workspace/to/run/codes #应改为项目工作目录
python [your_script].py #应改为项目python代码文件
```
* 使用命令`sbatch slurm_job.sbatch`提交计算任务

查看工作状态:
* 使用命令`squeue`查看slurm系统中任务的排队情况
* 查看工作目录下生成的`%j.out`和`%j.err`文件了解计算任务的工作状态
* 使用命令`scancel jobID`中止计算任务，其中jobID可通过`squeue`查询

> 更多高级功能指导，参见[SLURM快速入门用户指南](https://slurm.schedmd.com/quickstart.html)