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
### input为redis
```shell
input {
  redis {
    type => "sysMsg"
    host => "127.0.0.1"
    port => "6379"
    data_type => "list" # If redis_type is list, then we will BLPOP the key
    db => 0
    codec => "json"
    key => "palmplay_push_sysMsg_show"
  }
}
```
写入客户端用如下方法写入input就可以获得
```shell
rpush palmplay_push_sysMsg_show '{"name":"123","time": "2016-11-04 03:00:00"}'
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
