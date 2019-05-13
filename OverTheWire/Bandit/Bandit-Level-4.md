[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")
Credentials bandit3 UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

Level Goal

The password for the next level is stored in a hidden file in the inhere
directory. Commands you may need to solve this level

ls, cd, cat, file, du, find

ls -al total 24 drwxr-xr-x 3 root root 4096 Oct 16 2018 . drwxr-xr-x 41
root root 4096 Oct 16 2018 .. -rw-r--r-- 1 root root 220 May 15 2017
.bash_logout -rw-r--r-- 1 root root 3526 May 15 2017 .bashrc drwxr-xr-x
2 root root 4096 Oct 16 2018 inhere -rw-r--r-- 1 root root 675 May 15
2017 .profile bandit3@bandit:\~$ cd inhere bandit3@bandit:\~/inhere$ ls
bandit3@bandit:\~/inhere$ ls -al total 12 drwxr-xr-x 2 root root 4096
Oct 16 2018 . drwxr-xr-x 3 root root 4096 Oct 16 2018 .. -rw-r----- 1
bandit4 bandit3 33 Oct 16 2018 .hidden bandit3@bandit:\~/inhere$ cat
.hidden pIwrPrtPN36QITSp3EQaw936yaFoFgAB