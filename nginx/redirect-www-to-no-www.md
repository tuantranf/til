# Nginx rediret www to no-www

Redirect www.example.com to example.com
```
# Move the www people to no-www
server {
    listen 80;
    listen [::]:80; #enable for IPv6 support
    server_name www.example.com;
    return 301 scheme://example.com$request_uri;
}
```
