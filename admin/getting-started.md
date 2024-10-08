---
layout: default
title: Getting Started
parent: bootDNS-Admin Web Interface
nav_order: 2
has_children: false
---

# Getting Started

### 1. Download Docker
Since all components run in Docker, it is a requirement for bootDNS to have this installed, please see Dockers own guides at: [https://docs.docker.com/engine/install/](https://docs.docker.com/engine/install/)

### 2. Download bootDNS's docker-compose file
We have made it easy to get up and running, simply download this file: [docker-compose.yml](https://raw.githubusercontent.com/bootDNS/admin/main/docker-compose.yml) to a folder where you want to keep the database files.

Example:
```bash
user@host:~$ mkdir -p /opt/bootDNS
user@host:~$ cd /opt/bootDNS
user@host:/opt/bootDNS$ wget 'https://raw.githubusercontent.com/bootDNS/admin/main/docker-compose.yml' -O docker-compose.yml
```
    
### 3. Generate your APP_KEY
bootDNS-admin is using a PHP framework called Laravel, this requires a APP_KEY to be used in encryption of variables/cookies/passwords.
To get a unique key, run:

```bash
docker run --rm --entrypoint php ghcr.io/bootdns/admin:latest artisan key:generate --show
```

This will return something like:
```
base64:BAUup35vcapapEMV3m4+wL7+22Nu+oeLjEv4HpaxHvY=
```

In your newly downloaded docker-compose.yml file (step #2), open it with your favorite editor, and add your APP_KEY to the variable under admin "APP_KEY", which is empty.

### 4. Start it up! 
If you followed the docker installation guide, and you have populated your docker-compose.yml file with your APP_KEY, you should be good to go:

```bash
docker-compose up -d 
```

This will create the required containers; MariaDB for database, influxDB for DNS metrics, and the admin module.
Too see if its all running:

```bash
user@host:~$ docker ps
f3d13cc3b955   bootdns/admin:latest   "bash run.sh"            33 seconds ago   Up 31 seconds (healthy)   0.0.0.0:80->80/tcp, :::80->80/tcp                       bootdns-admin-1
ee74597810cd   influxdb:2.2                 "/entrypoint.sh infl…"   34 seconds ago   Up 32 seconds             0.0.0.0:8086->8086/tcp, :::8086->8086/tcp               bootdns-influxdb-1
040fb3c3ef61   mariadb:latest               "docker-entrypoint.s…"   34 seconds ago   Up 32 seconds             3306/tcp                                                bootdns-mariadb-1

```

You should now be able to access it via: http://HOSTNAME, default username/password is: admin / password

### 5. Setup your dns agent!
Now that you have the admin interface up and running, click on the [nameservers](/admin/nameservers.html) tab, generate a token and check out the guide for the agent, [here](/agent/getting-started.html)
