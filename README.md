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
