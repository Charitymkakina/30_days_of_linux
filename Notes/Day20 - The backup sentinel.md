# Mission
You are the "Backup Sentinel," the newly appointed system administrator for a promising tech startup. 
A recent, minor power surge caused a server glitch, momentarily corrupting a non-critical log file. 
While no important data was lost this time, it was a serious wake-up call.

The CTO has personally tasked you with a critical mission: 
-Implement a robust backup and recovery strategy for the company's main application server, and do it today. 
-The integrity of user data, application configurations, and vital logs is now in your hands.

# Task
# Solution

Step 1: Identify what must be backed

`User Data /home,`

`Application Data /var/www.`

`Logs /var/log.`

`Configurations /etc.`

Check if they exist:
`ls /home,`

`ls /var/www.`

`ls /etc.`

Step 2: Create a backup directory

`sudo mkdir -p /backup.`

`sudo chmod 700 /backup.`

Step 3: Create a manual backup

`sudo tar -czvf /backup/server_backup_$(date +%F).tar.gz \ /home /etc /var/www /var/log.`

Step 4: Verify the backup
`ls -lh /backup.`

Step 5: Test Recovery

`sudo mkdir /restore_test.`

`sudo tar -xzvf /backup/server_backup_2026-02-23.tar.gz -C /restore_test/.`

`Verify ls /restore_test/`

Tip: `check backup disk usage- df -h.`

Step 6: Automate Backup with Cron

`sudo crontab -e.`

`Daily backup at 2 AM: 02 * * * tar -czf /backup/server_backup_$(date +\%F).tar.gz /home /etc /var/www /var/log.`

`Check cron: sudo crontab -l.`

`Prevent backup overload: 03 * * * find /backup -type f -mtime +7 -delete (deletes backups older than 7 days).`
