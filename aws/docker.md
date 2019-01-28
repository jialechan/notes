```shell
sudo yum update -y
sudo yum install -y docker
sudo service docker start
# 将 ec2-user 添加到 docker 组，以便您能够执行 Docker 命令，而无需使用 sudo。
sudo usermod -a -G docker ec2-user
```

```shell
# mongo:3.4这个镜像名要在参数后面
docker run --name ci-mongo -p 27017:27017 -d  mongo:3.4 
docker run --name ci-redis -p 6379:6379 -d redis:5.0.3
docker run --name ic-mysql -e MYSQL_ROOT_PASSWORD=xxxxxx -p 3306:3306 -d mysql:5.7.25
```

