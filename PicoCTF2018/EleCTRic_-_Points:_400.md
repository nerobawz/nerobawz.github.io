[Category:Picoctf](/Category:Picoctf "wikilink") You came across a
custom server that Dr Xernon's company eleCTRic Ltd uses. It seems to be
storing some encrypted files. Can you get us the flag? Connect with nc
2018shell.picoctf.com 61333. Source.

from base64 import b64decode,b64encode flag_file =
"flag_b6f64afdd67b6ccc11f0.txt" known_cipher_b64 =
"Rh454/9J77XQgdtwOKBthUYeOeP/Se+10IHbcFOSUrk=" known_plaintext =
"ABCDEFGHABCDEFGHABCDEFGHABCD.txt" known_cipher =
b64decode(known_cipher_b64)

def encrypt(key,plaintext):

`   ret = bytearray()`
`   for i in range(len(plaintext)):`
`       ret.append(key[i%len(key)] ^ ord(plaintext[i]))`
`   return ret`

key = bytearray() for i in range(0,32):

`   key.append(known_cipher[i] ^ ord(known_plaintext[i]))`

print(key) print(b64encode(encrypt(key, known_plaintext)))

1.  Print actual encrypted text

print(b64encode(encrypt(key, flag_file)))

what happend here; well ctr mode without a nonce does always generate
the same encryption. and because it is xorrable if that means that a x b
= c - c x b = abs so there is a clear relation between the key,
plaintext and ciphertext

plaintext xor ciphertext gets you the keystream

picoCTF{alw4ys_4lways_Always_check_int3grity_6c094576}