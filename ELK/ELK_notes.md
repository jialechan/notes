## 根据时间删除数据
```shell
POST palmplay_push/sysMsg/_delete_by_query?conflicts=proceed
{
    "query": {
        "range" : {
            "@timestamp" : {
                "gte": "01/01/2016",
                "lte": "04/11/2016",
                "format": "dd/MM/yyyy||dd/MM/yyyy"
            }
        }
    }
}
```
