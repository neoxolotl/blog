---
title: "Cacti"
date: 2024-09-02T11:55:10Z
draft: true
---

Cacti create user admin passwd admin. After that you must change. 

```shell
version: '2'
services:
  cacti:
    image: "mrlesmithjr/cacti:latest"
    depends_on:
      - "db"
    links:
      - "db"
    ports:
      - "89:80"
      - "443:443"
    volumes:
      - "config:/config"
    restart: "always"
    environment:
      CACTI_DB: "cactidb"
      CACTI_DB_HOST: "db"
      CACTI_DB_PASSWORD: "cacti"
      CACTI_DB_USER: "cactiuser"
      CACTI_USER: "cactiuser"
      CACTI_USER_PASSWORD: "cacti"
  db:
    image: "mrlesmithjr/mysql:latest"
    volumes:
      - "db:/var/lib/mysql"
    restart: "always"
    environment:
      MYSQL_ROOT_PASSWORD: "cacti"
      MYSQL_DATABASE: "cactidb"
      MYSQL_USER: "cactiuser"
      MYSQL_PASSWORD: "cacti"

volumes:
  config:
  db:
```

