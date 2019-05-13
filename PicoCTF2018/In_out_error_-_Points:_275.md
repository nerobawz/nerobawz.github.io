[Category:Picoctf](/Category:Picoctf "wikilink") Can you utlize stdin,
stdout, and stderr to get the flag from this program? You can also find
it in /problems/in-out-error_3_9eb10797d687f70cfce62e7c9c2bdea6 on the
shell server

it wants Please may I have the flag? in stdin and seperate stdout and
stderr

`./in-out-error <<< "Please may I have the flag?" 1>/dev/null`

picoCTF{p1p1ng_1S_4_7h1ng_437b5c88}