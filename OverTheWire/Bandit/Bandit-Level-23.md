[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")

creds bandit22 Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI

Level Goal

A program is running automatically at regular intervals from cron, the
time-based job scheduler. Look in /etc/cron.d/ for the configuration and
see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful
skill. The script for this level is intentionally made easy to read. If
you are having problems understanding what it does, try executing it to
see the debug information it prints. Commands you may need to solve this
level

cron, crontab, crontab(5) (use “man 5 crontab” to access this)

cat /etc/cron.d/ cronjob_bandit22 cronjob_bandit23 cronjob_bandit24
.placeholder bandit22@bandit:\~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh &\> /dev/null

  - \* \* \* \* bandit23 /usr/bin/cronjob_bandit23.sh &\> /dev/null

bandit22@bandit:\~$ cat /usr/bin/cronjob_bandit23.sh

1.  \!/bin/bash

myname=$(whoami) mytarget=$(echo I am user $myname | md5sum | cut -d ' '
-f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname \> /tmp/$mytarget

echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349

cat /tmp/8ca319486bfbbc3663ea0fbe81326349
jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n