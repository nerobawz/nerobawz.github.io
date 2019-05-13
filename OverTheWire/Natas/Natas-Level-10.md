[Category:OverTheWire-Natas](/Category:OverTheWire-Natas "wikilink")

Username: natas10 nOpp1igQAkUzaI1GUUjzn1bFVj7xCNzu URL:
<http://natas10.natas.labs.overthewire.org>

we know grep allows for more that one file to be searched so we do a
/etc/natas_webpass/natas11 no results, so we know there is not an a in
the password. now we can iterate over untill we fine a right one. or we
use the -v invert-match parameter

\-v a /etc/natas_webpass/natas11

/etc/natas_webpass/natas11:U82q5TCMMQ9xuFoI3dYX61s7OZD9JKoK