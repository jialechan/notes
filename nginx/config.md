## nginx.conf
```shell
user  nobody;
worker_processes  2;

error_log  logs/error.log;
pid        logs/nginx.pid;

worker_rlimit_nofile 100000;
events {
    use epoll;
    worker_connections  49000;
}

http {
    include       mime.types;
    default_type  application/octet-stream;

    log_format chatLog 'T[$time_iso8601] STAT[$status] REQ_T[$upstream_response_time] URL[$request]';

    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  logs/access.log  main;

    sendfile        on;

    keepalive_timeout  65;

    gzip  on;

    server {
        listen       80;
        server_name  localhost;

        location / {
            root   html;
            index  index.html index.htm;
        }

        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }

    }

    include conf.d/*.conf;

}
```
