---
layout: default
title: Remote Query
parent: Modules
grand_parent: bootDNS-Admin Web Interface
nav_order: 1
has_children: false
---

### Remote Query

| Env        | Values           | Default  |
| ------------- |:-------------:| -----:|
| REMOTEQUERY_TYPE      | splunk / |  |


This makes it possible to pull zone data into the view of bootDNS.
Under a zone, there will be a "Remote Query" box, showing the results of the module.

#### Splunk

| Env        | Value           |
| ------------- |:-------------:|
| REMOTEQUERY_TYPE      | splunk |
| SPLUNK_SESSION_KEY      | (In Splunk) Settings -> Tokens |
| SPLUNK_URL | Splunk mgmt url+port, normally port 8089, fx. https://splunk.domain:8089/

Shows top 50 requested hosts, and percentile 


#### ELK

to be made
