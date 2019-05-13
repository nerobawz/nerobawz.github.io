[Category:Picoctf](/Category:Picoctf "wikilink")

`Here's a little website that hasn't fully been finished. But I heard google gets all your info anyway. `<http://2018shell.picoctf.com:11421>` (link) `

the hint aims that google gets all my information, so probably via a
google spider.

the google spider has Googlebot in its useragent so we do the same.

curl -A "Googlebot" <http://2018shell.picoctf.com:11421/flag> | grep
pico

picoCTF{s3cr3t_ag3nt_m4n_ed3fe08d}