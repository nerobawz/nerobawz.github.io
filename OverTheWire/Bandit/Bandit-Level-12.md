[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")
credentials bandit11 IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

Level Goal

The password for the next level is stored in the file data.txt, where
all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13
positions Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd Helpful
Reading Material

`   Rot13 on Wikipedia`

cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m' The password is
5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu