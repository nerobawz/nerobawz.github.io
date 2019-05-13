[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")

creds bandit16 cluFn7wTiGryunymYOu4RcffSxQluehd

Level Goal

The credentials for the next level can be retrieved by submitting the
password of the current level to a port on localhost in the range 31000
to 32000. First find out which of these ports have a server listening on
them. Then find out which of those speak SSL and which don’t. There is
only 1 server that will give the next credentials, the others will
simply send back to you whatever you send to it. Commands you may need
to solve this level

ssh, telnet, nc, openssl, s_client, nmap Helpful Reading Material

`   Port scanner on Wikipedia`

bandit16@bandit:\~$ nmap localhost -p 31000-32000

Starting Nmap 7.40 ( <https://nmap.org> ) at 2019-05-10 19:10 CEST Nmap
scan report for localhost (127.0.0.1) Host is up (0.00024s latency). Not
shown: 997 closed ports PORT STATE SERVICE 31046/tcp open unknown
31691/tcp open unknown 31790/tcp open unknown 31960/tcp open unknown

bandit16@bandit:\~$ openssl s_client -connect localhost:31790
CONNECTED(00000003) depth=0 CN = localhost verify error:num=18:self
signed certificate verify return:1 depth=0 CN = localhost verify
return:1 --- Certificate chain

`0 s:/CN=localhost`
`  i:/CN=localhost`

\--- Server certificate -----BEGIN CERTIFICATE-----
MIICBjCCAW+gAwIBAgIEcujsaTANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMTkwNDEwMTc0MDI2WhcNMjAwNDA5MTc0MDI2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwgZ8wDQYJKoZIhvcNAQEBBQADgY0AMIGJAoGBAMDAOx2/
Ga7z8/V6MZZt59YEZuKoMjCnGLvQRA10J/ax10I2sGzSShN8uHx3ywmE31uNlez0
/qWApc3c/SW2N7W+KFBlQ+2KAUaStDfa1q4vVFK9fjDqFMdrBH5M6xfkp6C29P7H
b5PjdyBUwa39Bzq6OmMCa43jR4a7rk7xf9ttAgMBAAGjZTBjMBQGA1UdEQQNMAuC
CWxvY2FsaG9zdDBLBglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0
ZWQgYnkgTmNhdC4gU2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3
DQEBBQUAA4GBAACt03iHqhg+NDoq/67pv7HgoEIdDeL9CemAvuiAYd3Njh97KI+6
Zfw2KJP4umFox/uicJLNqPLEvFmMCiUq5mIJc3DoQRJUFrem15mpDDtBvyYOi2eQ
kuRuSdEGJhl61CtLJ+srxuU9K7jFfzOrUL2K5bA2i7GhLalLbo5cMTXd -----END
CERTIFICATE----- subject=/CN=localhost issuer=/CN=localhost --- No
client certificate CA names sent Peer signing digest: SHA512 Server Temp
Key: X25519, 253 bits --- SSL handshake has read 1019 bytes and written
269 bytes Verification error: self signed certificate --- New, TLSv1.2,
Cipher is ECDHE-RSA-AES256-GCM-SHA384 Server public key is 1024 bit
Secure Renegotiation IS supported Compression: NONE Expansion: NONE No
ALPN negotiated SSL-Session:

`   Protocol  : TLSv1.2`
`   Cipher    : ECDHE-RSA-AES256-GCM-SHA384`
`   Session-ID: FD9E0AC99FAD5A37AA52D2EBDC5E03EB5457E6494FCC3E966C862A1BDE44CFA8`
`   Session-ID-ctx: `
`   Master-Key: 66A1CDEAC6D22C9969F03DA0849AC65F871B513A48ED058CAF949E1B5113CD45F2AD6D24B3973228E9977336CF371825`
`   PSK identity: None`
`   PSK identity hint: None`
`   SRP username: None`
`   TLS session ticket lifetime hint: 7200 (seconds)`
`   TLS session ticket:`
`   0000 - 80 db 3c 95 5a fe 5f ed-71 c2 67 d2 82 29 e8 58   ..<.Z._.q.g..).X`
`   0010 - b8 63 25 26 c3 08 82 28-55 96 35 0b 0a 04 33 bf   .c%&...(U.5...3.`
`   0020 - 2a 81 3c 85 03 41 bb e7-aa 66 61 ea 6c 23 71 71   *.<..A...fa.l#qq`
`   0030 - 0d 13 ec 2f 44 a4 f6 50-6a 45 41 58 00 6c ea 9c   .../D..PjEAX.l..`
`   0040 - 96 1d 7b 1f 3a 62 2a 8c-1b 40 eb c8 3f 3b 17 f6   ..{.:b*..@..?;..`
`   0050 - 18 5d 4c 69 41 a0 32 97-40 7c 1d 8c aa c6 c5 71   .]LiA.2.@|.....q`
`   0060 - 73 0b f8 8b e5 83 77 b4-9c c6 52 cf a5 3d b9 39   s.....w...R..=.9`
`   0070 - 08 9a 24 70 0c 77 5a 49-e3 da ea 81 ed d6 b4 39   ..$p.wZI.......9`
`   0080 - 21 39 db a4 0a b7 44 45-c6 2a 6c 56 31 ad 32 ca   !9....DE.*lV1.2.`
`   0090 - c7 a7 b4 17 3b ee 15 01-6b f3 12 e7 15 c6 fd 46   ....;...k......F`

`   Start Time: 1557508307`
`   Timeout   : 7200 (sec)`
`   Verify return code: 18 (self signed certificate)`
`   Extended master secret: yes`

\--- cluFn7wTiGryunymYOu4RcffSxQluehd Correct\! -----BEGIN RSA PRIVATE
KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY= -----END RSA
PRIVATE KEY-----

closed