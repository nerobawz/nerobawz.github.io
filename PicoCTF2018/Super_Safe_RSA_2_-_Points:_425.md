[Category:Picoctf](/Category:Picoctf "wikilink") Wow, he made the
exponent really large so the encryption MUST be safe, right?\! Connect
with nc 2018shell.picoctf.com 29483.

weiner attack

`  `
`from typing import Tuple, Iterator, Iterable, Optional`
`import binascii`
`  `
`def isqrt(n: int) -> int:`
`    if n == 0:`
`        return 0`
`  `
`    # ref: https://en.wikipedia.org/wiki/Methods_of_computing_square_roots#Rough_estimation`
`    x = 2 ** ((n.bit_length() + 1) // 2)`
`    while True:`
`        y = (x + n // x) // 2`
`        if y >= x:`
`            return x`
`        x = y`
`  `
`  `
`def is_perfect_square(n: int) -> bool:`
`    sq_mod256 = (1,1,0,0,1,0,0,0,0,1,0,0,0,0,0,0,1,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,1,1,0,0,1,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,1,0,0,0,0,0,0,1,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0)`
`    if sq_mod256[n & 0xff] == 0:`
`        return False`
`  `
`    mt = (`
`        (9, (1,1,0,0,1,0,0,1,0)),`
`        (5, (1,1,0,0,1)),`
`        (7, (1,1,1,0,1,0,0)),`
`        (13, (1,1,0,1,1,0,0,0,0,1,1,0,1)),`
`        (17, (1,1,1,0,1,0,0,0,1,1,0,0,0,1,0,1,1))`
`    )`
`    a = n % (9 * 5 * 7 * 13 * 17)`
`    if any(t[a % m] == 0 for m, t in mt):`
`        return False`
`  `
`    return isqrt(n) ** 2 == n`
`  `
`  `
`def rational_to_contfrac(x: int, y: int) -> Iterator[int]:`
`    while y:`
`        a = x // y`
`        yield a`
`        x, y = y, x - a * y`
`  `
`  `
`def contfrac_to_rational_iter(contfrac: Iterable[int]) -> Iterator[Tuple[int, int]]:`
`    n0, d0 = 0, 1`
`    n1, d1 = 1, 0`
`    for q in contfrac:`
`        n = q * n1 + n0`
`        d = q * d1 + d0`
`        yield n, d`
`        n0, d0 = n1, d1`
`        n1, d1 = n, d`
`  `
`  `
`def convergents_from_contfrac(contfrac: Iterable[int]) -> Iterator[Tuple[int, int]]:`
`    n_, d_ = 1, 0`
`    for i, (n, d) in enumerate(contfrac_to_rational_iter(contfrac)):`
`        if i % 2 == 0:`
`            yield n + n_, d + d_`
`        else:`
`            yield n, d`
`        n_, d_ = n, d`
`  `
`  `
`def attack(e: int, n: int) -> Optional[int]:`
`    f_ = rational_to_contfrac(e, n)`
`    for k, dg in convergents_from_contfrac(f_):`
`        edg = e * dg`
`        phi = edg // k`
`  `
`        x = n - phi + 1`
`        if x % 2 == 0 and is_perfect_square((x // 2) ** 2 - n):`
`            g = edg - phi * k`
`            return dg // g`
`    return None`
`  `
`e = 51894237144733210931794385100942482349013171036847530407252740499937774188291108716640058600385534835023044731027368135905917311839443286030527743928595328017887689553659234363258834192662580022497974100722635887085200696338628117424686300570634396830949980549603948203245407551079843395455119378005028748497`
`n = 65926041322679313887667841675592530544065988025158498106151098203931571430914832751074659232640668304313120930009704301831164279794169082666176179612474855651509836305289907228066977618234027539845630386915006221073901713924497601581046701735597398966791288290689041383471518599262730375121545655672717269777`
`c = 63618518268819218002306519139718509147725490299904921158709318571340788391392892094396167390592783713066886663710868499389854833189184226909424713992824959306165355792971823600212265867582655041677218572776288188459712080934699473517327818161571642865163687499385260254351901055920985170744019338404728910462`
`  `
`d = (attack(e,n))`
`  `
`plain = pow(c,d,n)`
`print(binascii.unhexlify(hex(plain)[2:]))`
`  `