存储库位置:`/data/disk0/Dataset`
分类:
* `Dataset`: 用于存放公共访问的手动下载的训练集
* `Eval`: 用于存放公共访问的模型Evaluation结果
* `home`: 被连接到`/data/disk0/Home`，因此原则上允许直接在自己的家目录下部署环境及存储资源，但对于没有特殊需求的项目而言，应当将其部署在`Workspace`下以便均衡存储负载
* `HuggingFace`: 曾用于链接HuggingFace的缓存目录，由于权限问题现已解除链接
* `Models`: 用于存放公共访问的手动下载的模型
* `Service`: 用于部署服务，已经为其创建PATH
* `Trash`: 用于保存通过`mv`删除的文件
* `Tutorial`: 用于存放教程和部署环境时使用的文件
* `Workspace`: 用于部署环境，个人环境应放在用户名同名目录下，团队环境应放在团队名同名目录下

权限:
* `Dataset`: `777`
* `Eval`: `777`
* `home`: `750`，非特殊情况由系统自动处理
* `HuggingFace`: `777`
* `Models`: `777`
* `Service`: `755`
* `Trash`: `600`
* `Tutorial`: `755`
* `Workspace`: 个人环境`700`，团队环境`770`
* 
下一节-[Hugging Face模型及数据集的下载](https://github.com/alkalimc/H100-Server-Guidebook/blob/main/chapter/general/huggingface.md)