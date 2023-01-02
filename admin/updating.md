---
layout: default
title: Updating
parent: bootDNS-Admin Web Interface
nav_order: 2
has_children: false
---

# Updating

Cd into your bootdns-admin directory, if you have followed our getting-started guide, it will be in: /opt/bootDNS

```
cd /opt/bootDNS
docker compose pull
docker compose up -d 
```

Done :) 

### Using a specific version

If you want to upgrade/downgrade to a specific version, you can check the docker tags out here: [https://hub.docker.com](https://hub.docker.com/repository/docker/terpz/bootdns/tags?page=1&ordering=last_updated&name=admin)
Then you need to edit the "image" tag in your docker-compose file

Be aware that downgrading the admin module is risky, since the database schema will not be downgraded, so changed fields made with your current version, might not be compatible with older versions
