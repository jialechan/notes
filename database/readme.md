### 查看所有表的记录行数
```sql
use information_schema;
select * from tables where TABLE_SCHEMA = 'xxx' order by table_rows desc;
```

### 查看慢记录
```sql
use mysql;
select * from slow_log order by start_time desc
```

### 查看数据库状态的一些命令
```sql 
show full processlist;
show engine innodb mutex;
show global status;
```
