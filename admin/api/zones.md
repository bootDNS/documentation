---
layout: default
title: Zones
parent: API Reference
grand_parent: bootDNS-Admin Web Interface
nav_order: 2
has_children: false
---

### Create New Zone

```http
POST /api/zone/{DOMAIN}
```

{: .note-title }
> Data to be send as json

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `ns` | `string, comma seperated` | **REQUIRED**. NS to allocate to this new zone |
| `active` | `int(1)` | **REQUIRED**. Zone active 1/0 |
| `dnssec` | `int(1)` | **OPTIONAL**. Enable DNSSEC 1/0 |
| `dsu` | `string` | **OPTIONAL**. Which DSU to use with DNSSEC (if any) |

##### Example
```bash
curl 'http://HOSTNAME/api/zone/example.com' \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer API-TOKEN' \
  --data-raw '{"ns":"ns1.domain.dk,ns2.domain.dk", "active":1 }
```

##### Response
```
{
    "error": "",
    "message": []
}
```
