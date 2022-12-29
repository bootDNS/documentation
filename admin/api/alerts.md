---
layout: default
title: Alerts
parent: API Reference
nav_order: 1
has_children: false
---
 
### Get Active Alerts

```http
  GET /api/alerts?clear=1/0
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `clear` | `int(1)` | **Optional**. Whether or not to clear alerts after fetching them (this clears for all users) |

##### Example
```bash
  curl 'http://HOSTNAME/api/alerts?clear=1' \
    --header 'Content-Type: application/json' \
    --header 'Authorization: Bearer API-TOKEN'
```

##### Response
```
{
    "error": "",
    "message": {
        "errorlog": [
            {
                "criticality": 2,
                "function": "pushZones",
                "function_id": 5,
                "function_name": "NameServer",
                "function_action": "pushNamedConf",
                "log": "Error when trying to push named.conf: Error when pushing: {\"error\":{\"message\":\"Checkconf validation failed.\"]}}",
                "latest_created_at": "2022-12-28 17:59:45",
                "count": 1
            }
        ]
    }
}
```
