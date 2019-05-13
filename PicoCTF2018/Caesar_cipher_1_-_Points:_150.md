[Category:Picoctf](/Category:Picoctf "wikilink") This is one of the
older ciphers in the books, can you decrypt the message? You can find
the ciphertext in
/problems/caesar-cipher-1_0_931ac10f43e4d2ee03d76f6914a07507 on the
shell server.

message = "yjhipvddsdasrpthpgrxewtgdqnjytto"

`for i in range(26):`
`   decode = ""`
`   for letter in message:`
`       if(ord(letter) - i < 97):`
`           rest = 97 - (ord(letter) - i)`
`           decode += chr(123-rest)`
`       else:`
`           decode += chr(ord(letter)-i)`
`   print(i,": ",decode)`

justagoodoldcaesarcipherobyujeez

picoCTF{justagoodoldcaesarcipherobyujeez}