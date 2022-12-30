---
layout: default
title: Traefik / Lego HTTPREQ Support
parent: Plugins / Addons
nav_order: 1
has_children: false
---

## The following must be set

```
provider: httpreq

HTTPREQ_ENDPOINT=http://your-bootdns-ip-or-host/api/lego
HTTPREQ_USERNAME=lego
HTTPREQ_PASSWORD=TOKEN-GENERATED-WITHIN-BOOTDNS
```
