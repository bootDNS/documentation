---
layout: default
title: Push Zones
parent: API Reference
grand_parent: bootDNS-Admin Web Interface
nav_order: 3
has_children: false
---

### Push Zone To Nameservers

```http
POST /api/push-zone/{DOMAIN}
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `DOMAIN` | `string` | **REQUIRED**. Which domain to push to NS |

##### Example
```bash
curl --request POST 'http://HOSTNAME/api/push-zone/example.com' \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer API-TOKEN'
```

##### Response
```
{
    "error": "",
    "message": [
        "29-12-22 05:42:26",
        "",
        "",
        "",
        "Generating configurations for server: ns1.server.dk (13.37.13.37), API: 13.37.13.37:25251, with type: standalone",
        "Getting current configuration and zones hashes",
        "Generating and sending acl.conf",
    ...........
```
