---
layout: default
title: Traefik
parent: Intergrations
grand_parent: bootDNS-Admin Web Interface
nav_order: 1
has_children: false
---

### Traefik Intergration

We dont have a native traefik dns provide, but we do support the dns provider plugin "[httpreq](https://go-acme.github.io/lego/dns/httpreq/)"

| Variable | Value |
| ------ | ------ |
| HTTPREQ_ENDPOINT | http(s)://your-bootdns-host:port/lego |
| HTTPREQ_USERNAME | bootdns |
| HTTPREQ_PASSWORD | A generated bootdns token from gui |
| HTTPREQ_PROPAGATION_TIMEOUT | 20 |
