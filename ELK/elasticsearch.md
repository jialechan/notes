## OOM相关
vim /etc/sysctl.conf
```shell
#添加两项
vm.overcommit_memory=1
vm.max_map_count=262144
```
命令行生效：sysctl -w vm.max_map_count=262144
