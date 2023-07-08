# NGINX Webserver

## Nginx webserver

Docker compose code to spin up an nginx webserver.

```
cd /opt
```

```
nano docker-compose.yml
```

This should be at the top of the docker-compose.yml file.

```
version: '3.8'
services:

```

Add the following code for the nginx container.

```
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

Save and then run the following command to spin up the container.

```
docker-compose up -d
```
