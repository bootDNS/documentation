---
layout: default
title: Nameservers
parent: bootDNS-Admin Web Interface
nav_order: 2
has_children: false
---

# Nameservers

To add a new nameserver, click on the "NameServers" tab.
Here you are able to see your current nameservers, their status and also the ability to create new.

### Create Nameserver
In the form "Create New NameServer", you can see the following fields:

| Field        | Description           | Example  |
| ------------- |:-------------| -----:|
| Host      | The external hostname of your nameserver | ns1.YOURDOMAIN.TLD |
| Ip      | The external ip of your nameserver      |   X.X.X.X |
| Agent Host | The internal host/ip of your nameserver      |    X.X.X.X |
| Agent Port | The port of the agent, you normally wont touch this field      |    25251 |
| Push Cron Schedule      | How often you want bootDNS to push out edited zones, in CRON format <br />default is every hour, check [crontab.guru](https://crontab.guru/), for more examples |   0 * * * * |
| Type      | **Standalone**: Every node is not dependent of anything, every node is its own master in most cases, you would use this <br />**Master**: For a master-slave setup, a master contains all zones and contains the "truth" <br />**Slave**: Caches zones from the master if needed     |    |
| Token      | This Token, is the authentication token from the Agent to the admin module, this is to be used when setting up an agent      |    |
| Extra     | In bootDNS, its possible to create your own type of NS, fx. if you want to push to AWS, you might need some extra variables to be set, its possbile to set them here, in json format, for normal use cases (standalone/master/slave) this is not needed | [ "APIKEY": "...." ]|

##### Setting up agent
See: [https://docs.bootdns.app/agent/getting-started.html](https://docs.bootdns.app/agent/getting-started.html)

### Flush Nameserver 
Sometimes it is nessersary to clear the cache of a nameserver, in the list of nameservers, click the little "toilet roll" to send a flush request to the agent
