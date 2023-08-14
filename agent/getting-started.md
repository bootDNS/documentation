---
layout: default
title: Getting Started
parent: bootDNS-Agent w. Bind
nav_order: 1
has_children: false
---

# Getting Started

### 1. Download Docker
Since all components run in Docker, it is a requirement for bootDNS to have this installed, please see Dockers own guides at: [https://docs.docker.com/engine/install/](https://docs.docker.com/engine/install/)

### 2. Download bootDNS's docker-compose file
We have made it easy to get up and running, simply download this file: [docker-compose.yml](https://github.com/bootDNS/bootDNS-agent/blob/main/docker-compose.yml?raw=true) to a folder where you want to keep the database files.

Example:
```bash
user@host:~$ mkdir -p /opt/bootDNS-agent
user@host:~$ cd /opt/bootDNS-agent
user@host:/opt/bootDNS-agent$ wget 'https://github.com/bootDNS/bootDNS-agent/blob/main/docker-compose.yml?raw=true' -O docker-compose.yml
```
    
### 3. Insert your token
From the admin panel, goto nameservers and create a new nameserver ([Nameservers Docs](https://docs.bootdns.app/admin/nameservers.html)) 
and insert into your newly downloaded docker-compose.yml file, after TOKEN=

### 4. Start it up!
```
docker compose up -d 
```
