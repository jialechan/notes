```sql
SELECT count(split_part(client, ':', 1)), split_part(client, ':', 1) AS ip
FROM "xxx-db"."xxx-table"
WHERE target_processing_time !=-1
        AND partition_0='2019'
        AND partition_1='06'
        AND partition_2='17'
        AND parse_datetime(log_timestamp,'yyyy-MM-dd''T''HH:mm:ss.SSSSSS''Z')
    BETWEEN parse_datetime('2019-06-17-06:00:00','yyyy-MM-dd-HH:mm:ss')
        AND parse_datetime('2019-06-17-07:00:00','yyyy-MM-dd-HH:mm:ss'))
GROUP BY split_part(client, ':', 1)
ORDER BY count(split_part(client, ':', 1)) desc
```
