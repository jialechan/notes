* ec2自带5分钟间隔的免费监控，监控维度包括cpu, 网络，硬盘。收费可以得到详细监控并且精确到1分钟。   
* 监控ec2内存使用的话，[需要安装agent](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/monitoring_ec2.html)   
* ec2停止后可以再启动，终止后就无法再启动。停止和终止不收费，只收取比如ebs存储的费用
* DynamoDB有golbal table功能，可以跨数据中心
* Kinesis是对标Kafka的队列，也可以跨数据中心
* 每个ec2创建就会分配一个公网ip,但是每次停止再启动后ip都会变，如果需要一个固定ip，需要一个叫做弹性ip地址的服务
* 可以为一个ec2实例添加网络接口（你就当是加一个网卡），然后再关联弹性ip到这个网络接口，那么这个ec2就有两个公网ip了
* 每个网络接口都有一个公网ip和私有ip, ec2是不知道任何关于她的公有ip的事情的
