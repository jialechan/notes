## 架构图
![架构图](https://docs.aws.amazon.com/zh_cn/glue/latest/dg/images/HowItWorks-overview.png)   
[详细](https://docs.aws.amazon.com/zh_cn/glue/latest/dg/components-key-concepts.html)

## AWS Glue 控制台工作流程概述
1. 使用表定义填充 AWS Glue 数据目录
2. 定义一个作业，该作业描述数据从源到目标的转换
3. 运行作业以转换数据
4. 监控您的已计划的爬网程序和已触发的作业   
[详细](https://docs.aws.amazon.com/zh_cn/glue/latest/dg/start-console-overview.html)

## 填充 AWS Glue 数据目录
![架构图](https://docs.aws.amazon.com/zh_cn/glue/latest/dg/images/PopulateCatalog-overview.png)     
[详细](https://docs.aws.amazon.com/zh_cn/glue/latest/dg/populate-data-catalog.html)

## 爬网程序运行时会出现什么情况
* 对数据分类，以确定原始数据的格式、架构和关联属性 – 您可以通过创建自定义分类器来配置分类结果。
* 将数据分组，至于表或分区中 – 根据爬网程序探试算法对数据分组。
* 将元数据写入 Data Catalog – 您可以配置爬网程序如何添加、更新和删除表和分区。   
[详情](https://docs.aws.amazon.com/zh_cn/glue/latest/dg/add-crawler.html#crawler-running)

## Amazon S3 文件夹是作为表还是作为分区创建的？
[详细](https://docs.aws.amazon.com/zh_cn/glue/latest/dg/add-crawler.html#crawler-s3-folder-table-partition)

## 注意
* 手动创建表的源数据的位置必须是 Amazon S3 路径
* 目前，使用控制台创建的分区表不能用于 ETL 作业。


