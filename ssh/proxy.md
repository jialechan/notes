## ssh代理
```bash
ssh -i /xxx.pem -qTfNn -D 9999 ubuntu@x.x.x.x -p 22
```
在本地开一个端口9999，将所有请求都转发到x.x.x.x这台服务器。   
是一个sokcet代理，可以用privoxy转化为一个web代理

## ssh隧道
```bash
ssh -i /xxx.pem -N -f -L 21196:y.y.y.y:21194 ubuntu@x.x.x.x -p 21194
```
