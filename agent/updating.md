---
layout: default
title: Updating
parent: bootDNS-Agent w. Bind
nav_order: 3
has_children: false
---

# Updating

Cd into your bootdns-agent directory, if you have followed our getting-started guide, it will be in: /opt/bootDNS-agent

```bash
user@host:~$ cd /opt/bootDNS-agent
user@host:/opt/bootDNS-agent$ docker compose pull
user@host:/opt/bootDNS-agent$ docker compose up -d 
```

If using with fluentd:

```bash
user@host:~$ cd /opt/bootDNS-agent
user@host:/opt/bootDNS-agent$ docker compose pull
user@host:/opt/bootDNS-agent$ docker compose -f docker-compose.yml -f docker-compose.fluentd.yml up -d
```

Done :) 

### Using a specific version

If you want to upgrade/downgrade to a specific version, you can check the docker tags out here: [https://hub.docker.com](https://hub.docker.com/repository/docker/terpz/bootdns/tags?page=1&ordering=last_updated&name=agent)
Then you need to edit the "image" tag in your docker-compose file
