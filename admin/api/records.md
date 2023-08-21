---
layout: default
title: Records
parent: API Reference
grand_parent: bootDNS-Admin Web Interface
nav_order: 4
has_children: false
---

### Create New Record

```http
POST /api/record/{DOMAIN}
```

{: .note-title }
> Data to be send as json

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `ttl` | `int` | **REQUIRED**. TTL in seconds |
| `type` | `string` | **REQUIRED**. a / cname ... |
| `value` | `string` | **REQUIRED**. Value of the record |
| `hostname` | `string` | **REQUIRED**. Which hostname of the record |

##### Example
```bash
curl --request POST 'http://HOSTNAME/api/record/example.com' \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer API-TOKEN' \
  --data-raw '{"ttl":"3600", "type": "a", "value":"1.1.1.1", "hostname":"@"}'
```

##### Response
```
{
    "error": "",
    "message": {
        "recordId": 4227
    }
}
```

---

### Edit Record By Hostname

```http
PUT /api/record/{DOMAIN}
```

{: .note-title }
> Data to be send as json

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `type` | `string` | **REQUIRED**. The type of which to edit |
| `value` | `string` | **REQUIRED**. Value of the record |
| `hostname` | `string` | **REQUIRED**. The hostname of which to edit |

##### Example
```bash
curl --request PUT 'http://HOSTNAME/api/record/example.com' \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer API-TOKEN' \
  --data-raw '{"type": "a", "value":"1.1.1.1", "hostname":"@"}'
```

##### Response
```
{
    "error": "",
    "message": {
    }
}
```

---

### Edit Record By RecordID

```http
PUT /api/record/{DOMAIN}/{RECORDID}
```

{: .note-title }
> Record id is provided when creating the record

{: .note-title }
> Data to be send as json

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `value` | `string` | **REQUIRED**. Value of the record |
| `ttl` | `string` | **REQUIRED**. TTL |

##### Example
```bash
curl --request PUT 'http://HOSTNAME/api/record/example.com/4227' \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer API-TOKEN' \
  --data-raw '{"value":"1.1.1.5", "ttl": 120}'
```

##### Response
```
{
    "error": "",
    "message": {
    }
}
```
