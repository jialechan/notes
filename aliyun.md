# 格式化硬盘
查看硬盘信息
```shell
fdisk -l
```
对硬盘进行分区
```shell
fdisk /dev/sdb
```
```shell
Command (m for help):n  
Command action  
　　   e    extended                  //输入e为创建扩展分区  
　　   p    primary partition (1-4)      //输入p为创建逻辑分区  
p  
Partion number(1-4)：1      //在这里输入l，就进入划分逻辑分区阶段了；  
First cylinder (51-125, default 51):   //注：这个就是分区的Start 值；这里最好直接按回车，如果您输入了一个非默认的数字，会造成空间浪费；  
Using default value 51  
Last cylinder or +size or +sizeM or +sizeK (51-125, default 125): +200M 注：这个是定义分区大小的，+200M 就是大小为200M ；当然您也可以根据p提示的单位cylinder的大小来算，然后来指定 End的数值。回头看看是怎么算的；还是用+200M这个办法来添加，这样能直观一点。如果您想添加一个10G左右大小的分区，请输入 +10000M ；  
  
Command (m for help): w                     //最后输入w回车保存。  
```
格式化硬盘
```shell
mkfs.ext4 /dev/sdb1
```
挂载硬盘
```shell
mkdir /data
mount /dev/sdb1 /data
```
配置开机自动挂载
```shell
vim /etc/fstab    
/dev/vdb1       /data   ext4    defaults 0 0
```

# ubuntu安装docker
## 先查看支持的docker版本
<a target="_blank"  href="https://rancher.com/docs/rancher/v1.6/zh/hosts/#docker%E7%89%88%E6%9C%AC%E9%80%82%E7%94%A8%E5%AF%B9%E6%AF%94">点击这里</a>
## 选一个版本安装
```shell
curl https://releases.rancher.com/install-docker/17.06.sh | sh
```

# 添加镜像（国内推荐）
```shell
vi /etc/docker/daemon.json
```
```shell
{ 
  "registry-mirrors": ["https://registry.docker-cn.com"] 
}
```
重启docker
```shell
systemctl daemon-reload 
systemctl restart docker
```

# 安装rancher
```shell
docker run -d --restart=unless-stopped -p 8080:8080 rancher/server:stable
```
