# SIMPLE BACKUP SCRIPT FOR A DOCKER HOST
Start from the official ubuntu documetation (https://ubuntu.com/server/docs/backups-shell-scripts) I created a simple backup file by adding the path where docker puts the container configuration and log files `/var/lib/docker/containers`.

## Executing the Script
The simplest way of executing the above backup script is to copy and paste the contents into a file. backup.sh for example. The file must be made executable:
> chmod u+x backup.sh
Then from a terminal prompt:
>sudo ./backup.sh

Use the cron utility to automate the script execution.
Enter the following from a terminal prompt:

`sudo crontab -e`

Add the following entry to the end of the `crontab` file:
> 0 0 * * * bash /***your***/***path***/backup.sh


## Restoring backup
To restore all files in the archive enter the following:
> cd /

> sudo tar -xzvf /mnt/backup/***file_name***.tgz