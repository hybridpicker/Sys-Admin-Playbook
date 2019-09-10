********************************
Schedule Tasks to run a set time
********************************
Mostyl with "crontab"

See if crontab is setup::

    crontab -l

Scenarion .txt-Files are uploaded in a directory and needs to be moved and archived::

      1 #!/bin/bash
      2 mv /home/hybridpicker/publicdir/* /home/hybridpicker/archive/
      3 echo"$(date) - files moved out of public directory by /home/hybridpicker/scripts.sh"      >> /home/hybridpicker/logs/move-and-backup.log

for get examples -> how to do cronjobs::

..image:: https://tecadmin.net/crontab-in-linux-with-20-examples-of-cron-schedule/

    https://tecadmin.net/crontab-in-linux-with-20-examples-of-cron-schedule/


Install new cronjobs with crontab -e::

    crontab -e

Schedule a cron to execute at 2am daily::

    0 2 * * * /home/hybridpicker/scripts/move-and-backup.sh

Schedule a cron to execute on every minutes::

    * * * * *  /home/hybridpicker/scripts/move-and-backup.sh

Schedule a cron to execute on every 10 minutes::

    */10 * * * * /home/hybridpicker/scripts/move-and-backup.sh

After saving::

    crontab: installing new crontab

Checking if cronjob is working::

    crontab -l

     * * * * *  /home/hybridpicker/scripts/move-and-backup.sh

Eventually -> Need to give writes for executing the cronjob.
