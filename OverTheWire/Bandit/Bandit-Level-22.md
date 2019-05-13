[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")

creds bandit21 gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr:

Level Goal

A program is running automatically at regular intervals from cron, the
time-based job scheduler. Look in /etc/cron.d/ for the configuration and
see what command is being executed. Commands you may need to solve this
level

cron, crontab, crontab(5) (use “man 5 crontab” to access this)

cat /etc/cron.d/cronjob_bandit22 @reboot bandit22
/usr/bin/cronjob_bandit22.sh &\> /dev/null

  - \* \* \* \* bandit22 /usr/bin/cronjob_bandit22.sh &\> /dev/null

bandit21@bandit:\~$ cat /usr/bin/cronjob_bandit22.sh

1.  \!/bin/bash

chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv cat
/etc/bandit_pass/bandit22 \> /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:\~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI