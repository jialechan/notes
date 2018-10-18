* ec2自带5分钟间隔的免费监控，监控维度包括cpu, 网络，硬盘。收费可以得到详细监控并且精确到1分钟。   
* 监控ec2内存使用的话，[需要安装agent](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/monitoring_ec2.html)   
* ec2停止后开可以启动，终止后就无法再启动。停止和终止不收费，只收取比如ebs存储的费用
* DynamoDB有golbal table功能，可以跨数据中心
* Kinesis是对标Kafka的队列，也可以跨数据中心
