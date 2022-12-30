---
layout: default
title: Query Logs via Fluentd
parent: bootDNS-Agent w. Bind
nav_order: 2
has_children: false
---

# Query Logs via Fluentd

If you want to export the query logs from Bind/Named within the agent, this can be done with our fluentd intergration.

### 1. Download fluentd compose file

```
#cd into where your agent docker-compose is present
user@host:/opt/bootDNS-agent$ wget 'https://github.com/bootDNS/bootDNS-agent/blob/main/docker-compose.fluentd.yml?raw=true' -O docker-compose.fluentd.yml
```

### 2. Configure fluentd
In the fluentd compose file, you will see some syslog parameters you need to change to your need, syslog_server / syslog_port / syslog_proto
```
    environment:
      - TZ=Europe/Copenhagen
      - syslog_server=192.168.4.104
      - syslog_port=2516
      - syslog_proto=udp

```
### 3. Start it!
Now, from now on when you want to start/recreate the agent, you need to run it with this, to include fluentd:
```
user@host:/opt/bootDNS-agent$ docker compose -f docker-compose.yml -f docker-compose.fluentd.yml up -d
```
