---
layout: default
title: Backup / Restore
parent: bootDNS-Admin Web Interface
nav_order: 9
has_children: false
---

# Backup / Restore


## Backup

Backup is created every day at 04:00, and is placed in the container, at location /restore.
In the default docker-compose.yml file, this folder is allready mapped.

The items in backup:
- Database (classic mysqldump)
- DNSSEC keys
- Crusial env variables from docker-compose.yml file (APP_KEY)

If a backup should fail backing up a step, fx. DNSSEC keys, the backup will still include database and variables, and the backup file will be labeled DATE_error.tar.gz, else if all succeed, DATE_full.tar.gz

### Manual Backup
If needed, its possible to trigger a manual backup using:
```bash
> cd /location/of/docker-compose/file
> docker compose exec admin php artisan backup:run --file=manual_backup
```
Which will create a file named "manual_backup.tar.gz" in the backup folder


## Restore
To restore from a backup:
```bash
> cd /location/of/docker-compose/file
> docker compose exec admin php artisan backup:restore --file=TAR.GZ-FILE-TO-RESTORE-FROM
```

This will start the restore program, and it will promth you with the APP_KEY that must replaced in your docker-compose.yml file, since this key is also used for encryption. (this can be done after the restore)
