[Category:Picoctf](/Category:Picoctf "wikilink") To be successful on
your mission, you must be able read data represented in different ways,
such as hexadecimal or binary. Can you get the flag from this program to
prove you are ready? Connect with nc 2018shell.picoctf.com 14390.

poh mooi tooltje

from pwn import \* import binascii

r = remote('2018shell.picoctf.com',14390) question1 = r.recv() print
question1 words = question1.split(' ')

answer1 = ""

for i in range(21,30):

`   if(words[i] == "as"):`
`       break`
`   n = int('0b'+str(words[i]), 2)`
`   answer1 += binascii.unhexlify('%x' % n)`
`   `

1.  print words\[item\]

print answer1 r.send(answer1 + "\\n") hexQ2 = r.recv().split(' ')\[4\]
print hexQ2 answer2 = binascii.unhexlify(hexQ2) print answer2
r.send(answer2 + "\\n")

question3 = r.recv() words = question3.split(' ') print words answer3 =
"" for i in range(5,len(words)):

`   print words[i]`
`   if(words[i] == "as"):`
`       break`
`   answer3 += chr(int(words[i],8))`

print answer3 r.send(answer3 + "\\n") question4 = r.recv() print
question4