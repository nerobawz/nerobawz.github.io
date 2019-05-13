[Category:Picoctf](/Category:Picoctf "wikilink") James Brahm, James
Bond's less-franchised cousin, has left his secure communication with HQ
running, but we couldn't find a way to steal his agent identification
code. Can you? Conect with nc 2018shell.picoctf.com 31123. Source.

the trick with this problem is that the key and the iv is always static
so every encryption round is the same

the output is in blocks of 16 bytes so we want to padd of to the left to
get a full block and then we fill in something like this:

AAAAAAAAAAAAAAAAAAAAAAAAAAifying code is: pBBBBBBBBBBBBBBBB

the a is to make sure the new block starts with ify code is: p and the
b's padd it to the next block.

this is so that when the cipher hits the actual part it is exactly the
same.

now we look if there are two matching blocks for every iteration we can
add a letter and brute force it.

picoCTF{@g3nt6_1$_th3_c00l3$t_6949075}