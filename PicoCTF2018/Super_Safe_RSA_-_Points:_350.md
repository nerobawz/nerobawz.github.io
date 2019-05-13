[Category:Picoctf](/Category:Picoctf "wikilink")

`Dr. Xernon made the mistake of rolling his own crypto.. Can you find the bug and decrypt the message? Connect with nc 2018shell.picoctf.com 6262. `

n has only two primes we found on <https://www.alpertron.com.ar/ECM.HTM>

13 583650 806475 814060 715396 647575 753149 690463 753059 662429 961062
685222 059061 045883 (80 digits) = 132 894095 989173 530655 802987
945442 347237 (39 digits) × 102214 102931 874655 384629 995413 576464
289759 (42 digits)

so if we have p q n e we can calculate the rest

t = (p-1)\*(q-1) d = inverse(e,t) p = pow(c,d,n)
bianscii.unhexlify(hex(int(p))\[2:\])
b'picoCTF{us3_l@rg3r_pr1m3$_3432}'