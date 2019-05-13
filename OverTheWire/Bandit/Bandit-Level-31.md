[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")
creds bandit31 47e603bb428404d265f59c42920d81e5

Level Goal

There is a git repository at
<ssh://bandit31-git@localhost/home/bandit31-git/repo>. The password for
the user bandit31-git is the same as for the user bandit31.

Clone the repository and find the password for the next level. Commands
you may need to solve this level

git

nano key.txt May I come in?

git add key.txt -f git commit -m "flag pls" git push

bandit:/tmp/412/repo$ git push Could not create directory
'/home/bandit31/.ssh'. The authenticity of host 'localhost (127.0.0.1)'
can't be established. ECDSA key fingerprint is
SHA256:98UL0ZWr85496EtCRkKlo20X3OPnyPSB5tB5RPbhczc. Are you sure you
want to continue connecting (yes/no)? yes Failed to add the host to the
list of known hosts (/home/bandit31/.ssh/known_hosts). This is a
OverTheWire game server. More information on
<http://www.overthewire.org/wargames>

bandit31-git@localhost's password: Counting objects: 3, done. Delta
compression using up to 4 threads. Compressing objects: 100% (2/2),
done. Writing objects: 100% (3/3), 317 bytes | 0 bytes/s, done. Total 3
(delta 0), reused 0 (delta 0) remote: \#\#\# Attempting to validate
files... \#\#\#\# remote: remote:
.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo. remote: remote: Well done\!
Here is the password for the next level: remote:
56a9bf19c63d650ce78e6ec0354ee45e remote: remote:
.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo. remote: To
<ssh://localhost/home/bandit31-git/repo>

`! [remote rejected] master -> master (pre-receive hook declined)`

error: failed to push some refs to
'<ssh://bandit31-git@localhost/home/bandit31-git/repo>'

56a9bf19c63d650ce78e6ec0354ee45e