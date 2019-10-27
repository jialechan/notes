```shell
fdiks -l
sudo mkfs -t ext4 /dev/xvdf
mkdir /data
mount /dev/xvdf /data
# 开机挂载
mkdir -p /etc/rc.d
vim /etc/rc.d/rc.local
mount /dev/xvdf /data
```
