﻿# find-ip

Add this Set header in nginx configuration for this app only then real ip address will show

```bash
server {
    listen 80;
    server_name your_domain.com;
    location / {
        proxy_pass http://your_nodejs_backend;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header CF-Connecting-IP $http_cf_connecting_ip;
    }
}
```
