[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")
creds bandit20 GbKksEFF4yrVs6il55v6gwY5aVje5f0j

Bandit Level 20 → Level 21 Level Goal

There is a setuid binary in the homedirectory that does the following:
it makes a connection to localhost on the port you specify as a
commandline argument. It then reads a line of text from the connection
and compares it to the password in the previous level (bandit20). If the
password is correct, it will transmit the password for the next level
(bandit21).

NOTE: Try connecting to your own network daemon to see if it works as
you think Commands you may need to solve this level

ssh, nc, cat, bash, screen, tmux, Unix ‘job control’ (bg, fg, jobs, &,
CTRL-Z, …)

screen

echo GbKksEFF4yrVs6il55v6gwY5aVje5f0j | nc -lp 1234 ctrl + a d

./suconnect 1234

screen -r

gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr