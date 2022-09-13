# SIMPLE BACKUP SCRIPT FOR A DOCKER HOST
Start from the official ubuntu documetation (https://ubuntu.com/server/docs/backups-shell-scripts) I created a simple backup file by adding the path where docker puts the container configuration and log files `/var/lib/docker/containers`.

## Executing the Script
Use the cron utility to automate the script execution.
Enter the following from a terminal prompt:

`sudo crontab -e`

Add the following entry to the end of the `crontab` file:
<code>
# m h dom mon dow   command
0 0 * * * bash /usr/local/bin/backup.sh
</code>

## Restoring backup
To restore all files in the archive enter the following:
<code>
cd /
sudo tar -xzvf /mnt/backup/***file_name***.tgz
</code>