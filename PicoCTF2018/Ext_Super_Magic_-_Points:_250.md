[Category:Picoctf](/Category:Picoctf "wikilink") We salvaged a ruined
Ext SuperMagic II-class mech recently and pulled the filesystem out of
the black box. It looks a bit corrupted, but maybe there's something
interesting in there. You can also find it in
/problems/ext-super-magic_3_debae27da9f20eec855067f3e83b45f3 on the
shell server.

<http://www.nongnu.org/ext2-doc/ext2.html#S-MAGIC>

we change the magic number to 53ef because of little endian style. at an
offset of 438 because it starts at 1024 and then an offset of 56 to the
magic number

the flag is in flag.jpg 0xEF53 picoCTF{Cd7AB187DFObAGeE3C3C7ea7E3B9DbEe}
picoCTF{Cd7AB187DF0bA6eE3c3c7ea7E3B9DbEe}