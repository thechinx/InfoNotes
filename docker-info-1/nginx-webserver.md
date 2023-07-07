# NGINX Webserver

## Nginx webserver

Docker compose code to spin up an nginx webserver.

```
cd /opt
```

```
nano docker-compose.yml
```

```
---
version: '3'
services:

  nginx:
    image: nginx
    container_name: nginx
    volumes:
     - /opt/nginx/templates:/etc/nginx/templates
     - /opt/nginx/src:/usr/share/nginx/html
    ports:
     - "80:80"
    environment:
     - NGINX_HOST=DOMAIN.NAME
     - NGINX_PORT=80
    restart: always

```

```
docker-compose up -d
```
