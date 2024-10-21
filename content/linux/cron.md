## Cron

###Cronjobs
- on ubuntu it is pretty easy to add a cronjob for timelengths like hour or daily. You can just add the script to
folder that corresponds in /etc/cron* 

using sudo before crontab -e will run the jobs as root 

### Cron settings for updates 

30 6 * * * root /usr/bin/apt update -q -y >> /var/log/apt/automaticupdates.log
31 6 * * * root /usr/bin/apt upgrade -q -y >> /var/log/apt/automaticupdates.log
30 22 * * * root /usr/bin/apt update -q -y >> /var/log/apt/automaticupdates.log
31 22 * * * root /usr/bin/apt upgrade -q -y >> /var/log/apt/automaticupdates.log
30 23 * * * root reboot
