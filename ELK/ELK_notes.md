### input为file的
```shell
input {
  file {
        type => "sysMsg"
        path => ["/Users/jialechan/log/mylog.log"]
        codec => "json"
        start_position => "beginning"
  }
}
```

### 根据时间删除数据
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

### 将json里面的field的时间转换为elasticsearch的时间
```shell
filter {
  date {
    match => [ "time", "YYYY-MM-dd HH:mm:ss" ]
  }
}
```
将json里面的time字段，按指定格式转化为elasticsearch的时间
