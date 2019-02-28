### 查看所有表的记录行数
```sql
use information_schema;
select sum(TABLE_ROWS) from tables where TABLE_SCHEMA = 'db_name';
```
