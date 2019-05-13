[Category:Picoctf](/Category:Picoctf "wikilink") Okay, so we found some
important looking files on a linux computer. Maybe they can be used to
get a password to the process. Connect with nc 2018shell.picoctf.com
38860. Files can be found here: passwd shadow.

passwd root:x:0:0:root:/root:/bin/bash shadow
root:$6$IGI9prWh$ZHToiAnzeD1Swp.zQzJ/Gv.iViy39EmjVsg3nsZlfejvrAjhmp5jY.1N6aRbjFJVQX8hHmTh7Oly3NzogaH8c1:17770:0:99999:7:::

this is a hash and the title refers to john the ripper

i used a wordlist in the SecLists repo.

john
--wordlist=/usr/share/wordlists/SecLists-master/Passwords/probable-v2-top1575.txt

john shadow --show root:password1:17770:0:99999:7:::

credentials: root password1

`nc 2018shell.picoctf.com 38860`

Username: root Password: password1 picoCTF{J0hn_1$_R1pp3d_4e5aa29e}