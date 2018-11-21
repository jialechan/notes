计算
* ec2自带5分钟间隔的免费监控，监控维度包括cpu, 网络，硬盘。收费可以得到详细监控并且精确到1分钟。   
* 监控ec2内存使用的话，[需要安装agent](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/monitoring_ec2.html)   
* ec2停止后可以再启动，终止后就无法再启动。停止和终止不收费，只收取比如ebs存储的费用
* 每个ec2创建就会分配一个公网ip,但是每次停止再启动后ip都会变，如果需要一个固定ip，需要一个叫做弹性ip地址的服务
* 可以为一个ec2实例添加网络接口（你就当是加一个网卡），然后再关联弹性ip到这个网络接口，那么这个ec2就有两个公网ip了
* 每个网络接口都有一个公网ip和私有ip, ec2是不知道任何关于她的公有ip的事情的
* ec2可以通过 curl -s http://169.254.169.254/latest/meta-data/local-ipv4 来获取私有ip
* ec2可以通过 curl -s http://169.254.169.254/latest/meta-data/public-ipv4 来获取公有ip

存储
* Glacier费用是s3的三分之一；从s3移动数据到Glacier大概花费24h左右时间；恢复数据到s3大概需要3~5h
* s3在上传新对象之后，立即提交的读请求会读到一致的数据。但是在更新或者删除操作之后的读请求操作将返回最终一直的结果（就是最终一样，但是有点延时）。
* 对象键用相同字母将限制s3存储桶的最大i/o性能。
* folder/object.png 这样的键从技术的本质上看，对象的键仍然是相同的folder开头
* 块状存储包含两类：网络附加存储；实例存储
* 网络附加存储通过网络附加到EC2实例。换句话要占网络带宽。
* 实例存储是主机系统提供的正常的物理磁盘
* 网络附加存储你可以几乎等同于EBS来看，EBS可以独立存在，不依靠ec2; 可靠性99.999%; 可以用s3作增量备份;可以在运行中备份;
* 实例存储必须依附到ec2, 费用包含在ec2里面；重启就丢数据；性能比EBS高（读3倍，写4倍）

RDS
* RDS创建块照的时候会暂停所有磁盘操作，请求可能会被推迟响应，甚至在超时候失败。
* 从快照恢复数据时，只能创建一个新的数据库，不能把快照恢复到一个已有的数据库
* 需要打开多AZ模式来启用RDS的高可用
* 创建读副本数据库可以改善数据库读性能

IAM：谁（身份认证）能做什么（授权）。使用IAM进行身份认证是通过用户/角色完成的，授权是通过策略完成的。
* IAM用户可以属于一个组，IAM角色不可以
* IAM用户不可以与一个EC2实例关联，IAM角色可以

其他
* DynamoDB有golbal table功能，可以跨数据中心
* Kinesis是对标Kafka的队列，也可以跨数据中心

-------------------------------------------------

VPC
* 如果你vpc有划分私有子网，那在私有子网里面的ec2必须要nat才可以访问其他aws资源（s3, dynamodb, kinesis等）,还有一个办法是用[vpn endpoint](https://docs.aws.amazon.com/zh_cn/vpc/latest/userguide/vpc-endpoints.html), 后者是一个更加好的实现，因为使用aws api的流量这样就不会离开Amazon 网络。


X-Ray
* [自定义分组](https://docs.aws.amazon.com/zh_cn/xray/latest/devguide/scorekeep-subsegments.html)
