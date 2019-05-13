[Category:Picoctf](/Category:Picoctf "wikilink") In a filesystem,
everything is relative ¯\\_(ツ)_/¯. Can you find a way to get a flag
from this program? You can find it in
/problems/absolutely-relative_4_bef88c36784b44d2585bb4d2dbe074bd on
the shell server. Source.

we see that the permissions file is relative ./permissions.txt and the
flag file is from root. so we make a dir in /tmp

mkdir /tmp/wotwot cd wotwot echo "yes" \> permissions.txt //run from
tmp/wotwot
/problems/absolutely-relative_4_bef88c36784b44d2585bb4d2dbe074bd/absolutely-relative

You have the write permissions. picoCTF{3v3r1ng_1$_r3l3t1v3_3b69633f}