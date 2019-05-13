[Category:OverTheWire-Natas](/Category:OverTheWire-Natas "wikilink")

Username: natas8 DBfUBfqQG69KvJvJ1iAbMoIpwSNQ9bWe URL:
<http://natas8.natas.labs.overthewire.org>

$encodedSecret = "3d3d516343746d4d6d6c315669563362";

function encodeSecret($secret) {

`   return bin2hex(strrev(base64_encode($secret)));`

}

php -a

echo
base64_decode(strrev(hex2bin("3d3d516343746d4d6d6c315669563362")));
secret is: oubWYf2kBq

Access granted. The password for natas9 is
W0mMhUcRRnG8dcghE4qvk3JA9lGt8nDl