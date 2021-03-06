## 安装
```shell
# 安装/定期更新
pip install awscli --upgrade --user

# 查看版本
aws --version
```

## 配置
```shell
# 配置profile为user2
aws configure --profile user2
```

## 配置优先顺序
命令行选项 > 环境变量 > CLI 凭证文件 > CLI 配置文件 > 容器凭证 > 实例配置文件凭证    
[详情](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-chap-configure.html#config-settings-and-precedence)

## 生成并使用参数骨架文件
```shell
aws ec2 run-instances --generate-cli-skeleton > ec2runinst.json
aws ec2 run-instances --cli-input-json file://ec2runinst.json
```
[详情](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-usage-skeleton.html)
