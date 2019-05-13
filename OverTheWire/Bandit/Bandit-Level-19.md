[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")

credentials bandit18 kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

Level Goal

The password for the next level is stored in a file readme in the
homedirectory. Unfortunately, someone has modified .bashrc to log you
out when you log in with SSH. Commands you may need to solve this level

ssh, ls, cat

ssh bandit.labs.overthewire.org -p 2220 -l bandit18 -t /bin/sh This is a
OverTheWire game server. More information on
<http://www.overthewire.org/wargames>

bandit18@bandit.labs.overthewire.org's password:

Permission denied, please try again.
bandit18@bandit.labs.overthewire.org's password: $ ls readme $ cat
readme IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x $