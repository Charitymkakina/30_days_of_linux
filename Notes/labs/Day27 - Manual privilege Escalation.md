# Linux Manual Privilege Escalation Guide

# Enumeration Methodology

checking current user- whoami

Check system information- cat /etc/os-release

sudo permissions

sudo -l

suid binaries

find / -perm -4000 -type f 2>/dev/null

cron jobs

cat /etc/crontab

ls -la /etc/cron*


