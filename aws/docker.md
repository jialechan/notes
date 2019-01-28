```shell
sudo yum update -y
sudo yum install -y docker
sudo service docker start
# 将 ec2-user 添加到 docker 组，以便您能够执行 Docker 命令，而无需使用 sudo。
sudo usermod -a -G docker ec2-user
```

```shell
docker run --name ci-mongo -p 27017:27017 -d mongo:3.4 
```
