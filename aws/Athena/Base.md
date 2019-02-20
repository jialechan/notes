https://github.com/rcongiu/Hive-JSON-Serde

> 您可以使用 AWS Glue 目录管理器来重命名列，但此时不能使用 AWS Glue 控制台更改表名称和数据库名称。要更正数据库名称，您需要创建一个新的数据库并将表复制到其中 (换言之，就是将元数据复制到新实体中)。对于表，您可以遵循类似的流程。您可以使用 AWS Glue SDK 或 AWS CLI 来完成此操作。

简单理解是列可以重命名，表和数据库不可以。
