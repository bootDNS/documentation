---
layout: default
title: CLI Commands
parent: bootDNS-Admin Web Interface
nav_order: 3
has_children: false
---

All scheduled jobs are run as "commands" inside the container, and can ofcourse be triggered manually

### Nameservers - Check (online/offline)
This command is to check if your ns is online or offline, if your ns have been offline, but are now online, it will re-push to that ns

```
docker compose exec -ti admin php artisan nameservers:check
```

---

### Nameservers - Get Health
Gets metrics of the ns and send to influx

```
docker compose exec -ti admin php artisan nameservers:health
```

---

### Nameservers - Get statistics
Get Bind statistics (query/query types/bind health) and generates new cache from those values

```
docker compose exec -ti admin php artisan nameservers:statistics
```

---

### Zones - Check
Tests the zones for errors, and checks for dnssec expiry

```
docker compose exec -ti admin php artisan zones:check {{--domain=}}
```

---

### Zones - DSU
Sends dsu for domains

```
docker compose exec -ti admin php artisan zones:dsu {{--domain=}}
```

---

### Zones - DSU
Get the raw zone file for domain

```
docker compose exec -ti admin php artisan zones:file {{--domain=}} {{--view=1}}
```


---

### Zones - Push
Push zone(s) to ns (same thing which is scheduled or via force push)

```
docker compose exec -ti admin php artisan zones:push {--ns=} {--domain=} {--force} {--ignoreErrors} {--restart} {--reload}
```
