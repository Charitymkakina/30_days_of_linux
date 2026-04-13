# Task
Your senior colleague is on a well-deserved vacation, and a critical task has just landed on your desk. 
The main application server is generating numerous log files, and they are quickly consuming disk space. 
Your mission, should you choose to accept it, is to become The Script Artisan.

You need to create an automated shell script to manage these log files. 
This isn't just about running a few commands; it's about building a robust, reusable tool. 
You'll start with a simple script and progressively add features like variables, user input, error checking, and loops. 
By the end of this challenge, you will have crafted a script that can back up and manage files, proving your value to the team and saving the day!

# Solution:
Step 1: Create a basic script
`nano log_manager.sh.`

`#!/bin/bash.`

`echo "Starting log backup...".`

`tar -czf /backup/log_backup_$(date +%F).tar.gz /var/log/myapp.`

`echo "Backup completed."`

`chmod +x log_manager.sh.`

`./log_manager.sh.`


Step 2: Introduce Variables

`#!/bin/bash.`

LOG_DIR="/var/log/myapp"

BACKUP_DIR="/backup"

DATE=$(date +%F)

BACKUP_FILE="$BACKUP_DIR/log_backup_$DATE.tar.gz"

`echo "Backing up logs from $LOG_DIR"`

`tar -czf $BACKUP_FILE $LOG_DIR`

echo "Backup saved as $BACKUP_FILE"

Step 3: Add user input

`#!/bin/bash`

`read -p "Enter log directory: " LOG_DIR.`

BACKUP_DIR="/backup"

DATE=$(date +%F)

BACKUP_FILE="$BACKUP_DIR/log_backup_$DATE.tar.gz"

`tar -czf $BACKUP_FILE $LOG_DIR`

`echo "Backup complete."`

Step 4: Add error checking
`#!/bin/bash`

`read -p "Enter log directory: " LOG_DIR`

if [ ! -d "$LOG_DIR" ]; then
    echo "Error: Directory does not exist!"
    exit 1
fi

BACKUP_DIR="/backup"
DATE=$(date +%F)
BACKUP_FILE="$BACKUP_DIR/log_backup_$DATE.tar.gz"

tar -czf $BACKUP_FILE $LOG_DIR

if [ $? -eq 0 ]; then
    echo "Backup successful."
else
    echo "Backup failed!"
fi

Step 5: Add loop to delete old logs
find $LOG_DIR -type f -mtime +7 -delete
echo "Old logs cleaned."

step 6: Automate with cron
crontab -e
