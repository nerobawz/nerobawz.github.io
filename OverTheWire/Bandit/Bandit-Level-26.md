[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")
creds bandit25 uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG Level Goal

Logging in to bandit26 from bandit25 should be fairly easy… The shell
for user bandit26 is not /bin/bash, but something else. Find out what it
is, how it works and how to break out of it. Commands you may need to
solve this level

ssh, cat, more, vi, ls, id, pwd

cat /etc/passwd | grep 26 bandit26:x:11026:11026:bandit level
26:/home/bandit26:/usr/bin/showtext

cat /usr/bin/showtext

1.  \!/bin/sh

export TERM=linux

more \~/text.txt exit 0

make screen smoll /v

  -
    e /etc/bandit_pass/bandit26

5czgV9L3Xx8JPOyRbXh6lQbmIOWvPT6Z

  -
    set shell=/bin/bash
    shell

./bandit27-do id uid=11026(bandit26) gid=11026(bandit26)
euid=11027(bandit27) groups=11026(bandit26) bandit26@bandit:\~$ ./
bandit27-do .ssh/ bandit26@bandit:\~$ ./bandit27-do cat
/etc/bandit_pass/bandit27 3ba3118a22e93127a4ed485be72ef5ea