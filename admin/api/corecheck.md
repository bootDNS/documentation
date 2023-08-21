---
layout: default
title: Core Health Check
parent: API Reference
grand_parent: bootDNS-Admin Web Interface
nav_order: 2
has_children: false
---

### Get BootDNS Core Health Status
```http
GET /api/core-check
```

Returns status 500 when something is wrong, else 200

> [!NOTE]
> This API dosnt require authentication

##### Example
```bash
curl 'http://HOSTNAME/api/core-check' \
  --header 'Content-Type: application/json' \
```

##### Response
```
{
  "ok": [
    "db",
    "scheduler",
    "redis",
    "apprise",
    "web"
  ],
  "failed": [
  ]
}
```
