# 格式化硬盘
https://blog.csdn.net/zqixiao_09/article/details/51417432  
vim /etc/fstab    
/dev/vdb1       /data   ext4    defaults 0 0

# ubuntu安装docker
## 先查看支持的docker版本
https://rancher.com/docs/rancher/v1.6/zh/hosts/#docker%E7%89%88%E6%9C%AC%E9%80%82%E7%94%A8%E5%AF%B9%E6%AF%94
## 选一个版本安装
curl https://releases.rancher.com/install-docker/17.06.sh | sh

# 安装rancher 
docker run -d --restart=unless-stopped -p 8080:8080 rancher/server:stable
