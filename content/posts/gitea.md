---
title: "Gitea"
date: 2024-08-23T13:47:43Z
title: Syncthing
---
Gitea Git Free
---

Usefull Git tools in your own home




Here source Code 

```shell
version: '2'
services:
  web:
    image: gitea/gitea:1.7.1
    volumes:
      - ./data:/data
    ports:
      - "3000:3000"
      - "2233:2233"
    depends_on:
      - db
    restart: always
  db:
    image: mariadb:10
    restart: always
    environment:
      - MYSQL_ROOT_PASSWORD=Pass02!a
      - MYSQL_DATABASE=gitea
      - MYSQL_USER=gitea
      - MYSQL_PASSWORD=Pass02!a
    volumes:
      - ./db/:/var/lib/mysql
```

this is all after that can you see in your browser. Only need open the port 3000. Remember add your data access user and password. 
