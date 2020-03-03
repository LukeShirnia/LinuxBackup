# LinuxBackup
Backup your Linux filesystme on a cron using this script (includes tar, gpg encryption and rsync)


## Example desktop backup script crons
```
30 15 * * * /usr/bin/desktop-backup daily >> /root/backups_desktop/daily-status.log 2>&1
00 15 * * FRI /usr/bin/desktop-backup weekly >> /root/backups_desktop/weekly-status.log 2>&1
00 8 1 * * /usr/bin/desktop-backup monthly >> /root/backups_desktop/monthly-status.log 2>&1
```

## Example multiple domain backup script crons
Prerequisites:
- holland-mysqldump (+ dependencies)

```
30 15 * * * holland -q bk; /usr/bin/domains-backup daily >> /var/log/backup-script-daily-status.log 2>&1
00 15 * * FRI holland -q bk; /usr/bin/doamins-backup weekly >> /var/log/backup-script-weekly-status.log 2>&1
00 8 1 * * holland -q bk; /usr/bin/domsins-backup monthly >> /var/log/backup-script-monthly-status.log 2>&1
```