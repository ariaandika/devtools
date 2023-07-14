# NGINX

nginx is a web server, reverse proxy and cache server. Can be used as entry point of a server

## Main Control

nginx controlled from the command line

```sh
nginx -s [signal]
```

signals:

1. reload, graceful reload
2. reopen, reopen the log files
3. stop, fast shutdown
4. quit, graceful shutdown

get list of running nginx servers

```bashsh
ps -ax | grep nginx
```

## Configuration

custom prefix, prefix is root for configuration directory

```bash
nginx -p /home/user/dev/nginx/
```

custom config file

```bash
nginx -c /home/user/dev/nginx/nginx.conf
```

servers

```nginx
http {
  
  server {
    # Proxy
    location / {
      proxy_pass http://localhost:8080;
    }
    
    # static assets
    location /public/ {
      root /data;
    }
    
    # wildcard
    location ~ \.(gif|jpg|png)$ {
      root /data/images;
    }
  }
  
  # Proxy handler
  server {
    listen 8080;
    root /data/up1;

    location / {
      
    }
  }
}
```

directives, written without blocks

```nginx
user             nobody;
error_log        logs/error.log notice;
worker_processes 1;

include conf.d/http;
include conf.d/stream;
include conf.d/exchange-enhanced;
```
