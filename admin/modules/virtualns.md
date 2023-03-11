---
layout: default
title: Virtual NS
parent: Modules
grand_parent: bootDNS-Admin Web Interface
nav_order: 2
has_children: false
---

### Virtual Name Server

Its possible to make a virtual ns, meaning it could be Route 53 in AWS you also deploy your zones to.

Right now there is only AWS (which is not working) but this module makes it possible to code your own if you need it to support your cloud provider.

Code and AWS example can be found on [git](https://github.com/bootDNS/bootDNS-admin/tree/main/app/virtualNS)


#### Virtual Nameservers Supported
| System        | Desc           |
| ------------- |:-------------:|
| Amazon Route 53  |          |
