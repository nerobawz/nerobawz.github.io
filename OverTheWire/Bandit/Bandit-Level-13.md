[Category:OverTheWire-Bandit](/Category:OverTheWire-Bandit "wikilink")
credentials bandit 12 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

Level Goal

The password for the next level is stored in the file data.txt, which is
a hexdump of a file that has been repeatedly compressed. For this level
it may be useful to create a directory under /tmp in which you can work
using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile
using cp, and rename it using mv (read the manpages\!) Commands you may
need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp,
mv, file Helpful Reading Material

`   Hex dump on Wikipedia`

cd /tmp/wotwot bandit12@bandit:/tmp/wotwot$ ls data.txt data.txt.bk
test.bz2 bandit12@bandit:/tmp/wotwot$ file test.bz2 test.bz2: gzip
compressed data, was "data2.bin", last modified: Tue Oct 16 12:00:23
2018, max compression, from Unix bandit12@bandit:/tmp/wotwot$ mv
test.bz2 data2.bin bandit12@bandit:/tmp/wotwot$ man 7z No manual entry
for 7z (Alternatively, what manual page do you want from section 7z?)
bandit12@bandit:/tmp/wotwot$ tar zxvf data2.bin tar: This does not look
like a tar archive tar: Skipping to next header tar: Exiting with
failure status due to previous errors bandit12@bandit:/tmp/wotwot$ gzip
-d data2.bin gzip: data2.bin: unknown suffix -- ignored
bandit12@bandit:/tmp/wotwot$ clear

bandit12@bandit:/tmp/wotwot$ file data2.bin data2.bin: gzip compressed
data, was "data2.bin", last modified: Tue Oct 16 12:00:23 2018, max
compression, from Unix bandit12@bandit:/tmp/wotwot$ mv data2.bin
data2.bin.gz bandit12@bandit:/tmp/wotwot$ gunzip data2.bin.gz
bandit12@bandit:/tmp/wotwot$ ls data2.bin data.txt data.txt.bk
bandit12@bandit:/tmp/wotwot$ cat data2.bin
���h��6��@4�bi���h������￻����������׽��9��

`   �mF�h�h44`

��B��,0� ��4@�����@2�C@h�� �
�ɋ�^-K�����}�\\,�ǿ�}E�F�_\!r�U�g?E�i��9x��TB@�lȲ���BF.hM�SC4�V�F�R�Br"�\<(Hت$
$���KBs��%l�\~�_�ݿ���g�zM�w�\#P"2@������

��\\��WQO4�p�i����S�\#&��/�\#��\[j���\<D�uԐ^_�H.�-��wAt

`                                                 �[��UP�G�CP��&:�2�*�)�\�������H�`

�\\�bandit12@bandit:/tmp/wotwot$ file data2.bin data2.bin: bzip2
compressed data, block size = 900k bandit12@bandit:/tmp/wotwot$ mv
data2.bin data2.bin.tar.bz2 bandit12@bandit:/tmp/wotwot$ file
data2.bin.tar.bz2 data2.bin.tar.bz2: bzip2 compressed data, block size =
900k bandit12@bandit:/tmp/wotwot$ tar xvf data2.bin.tar.bz2
bandit12@bandit:/tmp/wotwot$ ls data2.bin.tar.bz2 data.txt data.txt.bk
bandit12@bandit:/tmp/wotwot$ file data2.bin.tar.bz2 data2.bin.tar.bz2:
bzip2 compressed data, block size = 900k bandit12@bandit:/tmp/wotwot$
tar jxvf data2.bin.tar.bz2 bandit12@bandit:/tmp/wotwot$ ls
data2.bin.tar.bz2 data.txt data.txt.bk bandit12@bandit:/tmp/wotwot$ ls
data2.bin.tar.bz2 data.txt data.txt.bk bandit12@bandit:/tmp/wotwot$
mkdir kek bandit12@bandit:/tmp/wotwot$ cp data2.bin.tar.bz2 kek
bandit12@bandit:/tmp/wotwot$ cd kek bandit12@bandit:/tmp/wotwot/kek$ ls
data2.bin.tar.bz2 bandit12@bandit:/tmp/wotwot/kek$ file
data2.bin.tar.bz2 data2.bin.tar.bz2: bzip2 compressed data, block size =
900k bandit12@bandit:/tmp/wotwot/kek$ bzip2 -k9 data2.bin.tar.bz2 bzip2:
Input file data2.bin.tar.bz2 already has .bz2 suffix.
bandit12@bandit:/tmp/wotwot/kek$ bzip2 -vd data2.bin.tar.bz2

` data2.bin.tar.bz2: done`

bandit12@bandit:/tmp/wotwot/kek$ ls data2.bin.tar
bandit12@bandit:/tmp/wotwot/kek$ file data2.bin.tar data2.bin.tar: gzip
compressed data, was "data4.bin", last modified: Tue Oct 16 12:00:23
2018, max compression, from Unix bandit12@bandit:/tmp/wotwot/kek$ mv
data2.bin.tar data2.bin.gz bandit12@bandit:/tmp/wotwot/kek$ mv
data2.bin.gz data2.tar.gz bandit12@bandit:/tmp/wotwot/kek$ tar zxvf
data2.tar.gz data5.bin bandit12@bandit:/tmp/wotwot/kek$ ls data2.tar.gz
data5.bin bandit12@bandit:/tmp/wotwot/kek$ file data5 data5: cannot open
\`data5' (No such file or directory) bandit12@bandit:/tmp/wotwot/kek$ ls
-al total 24 drwxr-sr-x 2 bandit12 root 4096 May 10 18:49 . drwxr-sr-x 3
bandit12 root 4096 May 10 18:46 .. -rw-r--r-- 1 bandit12 root 435 May 10
18:46 data2.tar.gz -rw-r--r-- 1 bandit12 root 10240 Oct 16 2018
data5.bin bandit12@bandit:/tmp/wotwot/kek$ cat data5.bin
4Ƅ�E�����F�M�644000000000000000000000034113361351327011247
0ustar rootrootBZh91AY\&SY6E���Y�@�U��Z��t\!ހ��u�� �

`2ɉ��bhi���A�@�*���!Ycu�    ���I�����W*���aٻ~�׼9��Y����,�!YK�ZA4R|;-g��e2���4O��؇���&��1�t��Dx��]s�y������e��&b�]��B@�@bandit12@bandit:/tmp/wotwot/kek$ `

bandit12@bandit:/tmp/wotwot/kek$ file data5.bin data5.bin: POSIX tar
archive (GNU) bandit12@bandit:/tmp/wotwot/kek$ mv data5.bin
data5.bin.tar bandit12@bandit:/tmp/wotwot/kek$ tar xvf data5.bin.tar
data6.bin bandit12@bandit:/tmp/wotwot/kek$ file data6.bin data6.bin:
bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/wotwot/kek$ mv data6.bin data6.bin.tar.bz2
bandit12@bandit:/tmp/wotwot/kek$ tar jxvf data6.bin.tar.bz2 data8.bin
bandit12@bandit:/tmp/wotwot/kek$ file data8.bin data8.bin: gzip
compressed data, was "data9.bin", last modified: Tue Oct 16 12:00:23
2018, max compression, from Unix bandit12@bandit:/tmp/wotwot/kek$ mv
data8.bin data8.bin.tgz bandit12@bandit:/tmp/wotwot/kek$ tar zxvf
data8.bin.tgz bandit12@bandit:/tmp/wotwot/kek$ ls data2.tar.gz
data5.bin.tar data6.bin.tar.bz2 data8.bin.tgz
bandit12@bandit:/tmp/wotwot/kek$ file data8.bin.tgz data8.bin.tgz: gzip
compressed data, was "data9.bin", last modified: Tue Oct 16 12:00:23
2018, max compression, from Unix bandit12@bandit:/tmp/wotwot/kek$ mv
data8.bin.tgz data8.gz bandit12@bandit:/tmp/wotwot/kek$ gunzip data8.gz
bandit12@bandit:/tmp/wotwot/kek$ ls data2.tar.gz data5.bin.tar
data6.bin.tar.bz2 data8 bandit12@bandit:/tmp/wotwot/kek$ cat data0 cat:
data0: No such file or directory bandit12@bandit:/tmp/wotwot/kek$ cat
data8 The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
bandit12@bandit:/tmp/wotwot/kek$