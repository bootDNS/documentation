---
layout: default
title: Traefik / Lego Support
parent: Plugins / Addons
nav_order: 1
has_children: false
---

## Traefik / Lego HTTPREQ Support

We dont have a native traefik dns provider, but we do support the dns provider plugin "[httpreq](https://go-acme.github.io/lego/dns/httpreq/)"

| Variable | Value |
| ------ | ------ |
| HTTPREQ_ENDPOINT | http(s)://your-bootdns-host:port/lego |
| HTTPREQ_USERNAME | bootdns |
| HTTPREQ_PASSWORD | A generated bootdns token from gui |
| HTTPREQ_PROPAGATION_TIMEOUT | 20 |

The Token generated must have the "zones-edit" capability
