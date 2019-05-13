[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")

creds bandit23 jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n Level Goal

A program is running automatically at regular intervals from cron, the
time-based job scheduler. Look in /etc/cron.d/ for the configuration and
see what command is being executed.

NOTE: This level requires you to create your own first shell-script.
This is a very big step and you should be proud of yourself when you
beat this level\!

NOTE 2: Keep in mind that your shell script is removed once executed, so
you may want to keep a copy around… Commands you may need to solve this
level

cron, crontab, crontab(5) (use “man 5 crontab” to access this)

bandit23@bandit:/tmp/wotwot23$ cat bandit24
bandit23@bandit:/tmp/wotwot23$ rm bandit24
bandit23@bandit:/tmp/wotwot23$ ls bandit23@bandit:/tmp/wotwot23$ touch
bandit24.sh bandit23@bandit:/tmp/wotwot23$ ls bandit24.sh
bandit23@bandit:/tmp/wotwot23$ chmod 777 bandit24.sh
bandit23@bandit:/tmp/wotwot23$ ls bandit24.sh
bandit23@bandit:/tmp/wotwot23$ vi bandit24.sh
bandit23@bandit:/tmp/wotwot23$ cat bandit24.sh

1.  \!/bin/bash

cat /etc/bandit_pass/bandit24 \>\> /tmp/wotwot23/bandit24
bandit23@bandit:/tmp/wotwot23$ cp bandit24.sh /var/spool/bandit24/
bandit23@bandit:/tmp/wotwot23$ ls bandit24.sh
bandit23@bandit:/tmp/wotwot23$ ls bandit24.sh
bandit23@bandit:/tmp/wotwot23$ ls /var/spool/bandit24/ ls: cannot open
directory '/var/spool/bandit24/': Permission denied
bandit23@bandit:/tmp/wotwot23$ ls /var/spool/bandit24 ls: cannot open
directory '/var/spool/bandit24': Permission denied
bandit23@bandit:/tmp/wotwot23$ ls /var/spool/bandit24 ls: cannot open
directory '/var/spool/bandit24': Permission denied
bandit23@bandit:/tmp/wotwot23$ ls /var/spool/bandit24/ ls: cannot open
directory '/var/spool/bandit24/': Permission denied
bandit23@bandit:/tmp/wotwot23$ ls bandit24.sh