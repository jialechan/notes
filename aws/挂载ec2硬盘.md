```shell
fdisk -l
sudo mkfs -t ext4 /dev/xvdf
mkdir /data
mount /dev/xvdf /data
# 开机挂载
```shell
# 查看磁盘分区的UUID
sudo blkid
# 配置开机自动挂载：
vim /etc/fstab
UUID=11263962-9715-473f-9421-0b604e895aaa /data ext4 defaults 0 1
# 运行验证
sudo mount -a
```
