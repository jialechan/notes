# Notes
### 查看链接数
```shell
netstat -an|grep ESTABLISHED|wc -l
```
### 查看gc情况
```shell
jstat -gc 12538 1000
```
查看pid为12538的情况，每1秒显示一次
### 查看cpu
```shell
cat /proc/cpuinfo
```

### 查看什么程序ip访问8080端口
```shell
netstat -natp|grep 8080
```
### 查看文件夹占用空间并排序
```shell
du -h --max-depth=1 | sort -rn
```
### 获取公网ip
```shell
curl https://www.taobao.com/help/getip.php
```
### 每天0点删除某目录下包含.log的而且是10天前
```shell
00 00 * * * find /userdata1/logs/dmenu -mtime +10 -name "*.log*" -exec rm -rf {} \;
```
