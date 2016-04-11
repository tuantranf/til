# Redirect http to https

Redirect http://example.com to https://example.com

```
server {
  	listen 80;
  	listen [::]:80; #enable for IPv6 support
  	server_name example.com;
  	return 301 https://example.com$request_uri;
}

server {
  	listen 443 ssl;
  	listen [::]:443 ssl;
  	server_name example.com;
  
  	# ssl_certificate
  	ssl_certificate /path/to/cert/file;
  	ssl_certificate_key /path/to/cert/key/file;
  
    location / {
    }

    # 
}
```
