---
layout: default
title: Notifications
parent: bootDNS-Admin Web Interface
nav_order: 10
has_children: false
---

# Notifications

We count build our own framework, which supported the basic chat providers, but instead we choose to use [Apprise](https://github.com/caronc/apprise) which as they say:
> Apprise allows you to send a notification to almost all of the most popular notification services available to us today such as: Telegram, Discord, Slack, Amazon SNS, Gotify, etc.

To see the full list of supported services, check [here](https://github.com/caronc/apprise#productivity-based-notifications)

## Setup
In our docker compose file, apprise is allready included, we dont store any configurations in this, we just use it as a gateway.

In BootDNS, goto Settings->Notifications, here you will be able to create a new service, and also define what you want to send to it. 
The "Module" input, defines the Apprise module you want to use, see this [list](https://github.com/caronc/apprise#productivity-based-notifications) for syntax, and also how to get the needed info such as api keys if needed.

And example of the input could be, if using Telegram:
> tgram://BOT-TOKEN/ChatID

or mail:
> mailto://domain.com?smtp=my-smtp-server.com&from=noreply@domain.com&to=me@domain.com
