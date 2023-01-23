---
layout: post
title: Nginx reverse proxy in docker
---




## Why using reverse proxy
I have hosting multiple docker container to serve my home service and testing project. 
Most of them have a web UI but they may conflit by sharing the same port.
Therefore, I want to use a reverse proxy service to isolate them in a seperated network.

### My walkthrough
I am using the offical image from Nginx with version `1.21`.

`docker pull nginx:1.21`

I than create a compose file.
````yml
version: '3'
services:
    reverse-proxy:
        image: nginx:1.21
        profiles: ["proxy"]
        volumes:
            - ./docker-data/reverse-proxy/html:/usr/share/nginx/html
            - ./docker-data/reverse-proxy/cert:/etc/ssl/certs/nginx
            - ./docker-data/reverse-proxy/conf:/etc/nginx
        ports:
            - "80:80"
```