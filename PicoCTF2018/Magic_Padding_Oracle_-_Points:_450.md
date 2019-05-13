[Category:Picoctf](/Category:Picoctf "wikilink") Can you help us
retreive the flag from this crypto service? Connect with nc
2018shell.picoctf.com 4966. We were able to recover some Source Code.

`  `
`  `
`from pwn import *`
`  `
`context.log_level = 'warn'`
`  `
`def xor(s1, s2):`
`    return ''.join(chr(ord(x) ^ ord(y)) for x, y in zip(s1, s2))`
`  `
`def str_replace(text,index=0,replacement=''):`
`    return '%s%s%s'%(text[:index],replacement,text[index+1:])`
`  `
`target = [`
`    '{"username": "gu',`
`    'est", "expires":',`
`    ' "2030-01-07", "',`
`    'is_admin":  "tru',`
`    'e"}'+'\x0d'*13`
`]`
`  `
`iv = 'This is an IV456'`
`  `
`block = [`
`    iv,`
`    '0'*16,`
`    '0'*16,`
`    '0'*16,`
`    '0'*16,`
`    'A'*16`
`]`
`  `
`#skip the last block but go from last to first`
`for n_block in range(len(block)-2,-1,-1):`
`    `
`    #for every byte in the block`
`    for i in range(16):`
`        print 'Guessing [{}]-byte'.format(15-i)`
`        for j in range(200,256):`
`            print(j)`
`  `
`            #replace the current character in the block `
`            block[n_block] = str_replace(block[n_block], 15-i, chr(j))`
`  `
`            #ciphertext is the current row of block and the row above in hex`
`            ciphertext = (block[n_block]+block[n_block+1]).encode('hex')`
`  `
`            r = remote('2018shell.picoctf.com',4966)`
`  `
`            r.recvuntil('What is your cookie?\n')`
`            r.sendline(ciphertext)`
`            response = r.recv()`
`            print(response)`
`            #if it is a valid padding schema`
`            if response.find('invalid padding') == -1:`
`                #for k in range of current index of block + 1`
`                for k in range(i+1):`
`                    #if it is the last one do nothing`
`                    if i == 15:`
`                        break`
`  `
`  `
`                    print(ord(block[n_block][15-k]))`
`                    print(i+1)`
`                    print(i+2)`
`                    new_val = chr(ord(block[n_block][15-k]) ^ (i+1) ^ (i+2))`
`                    #print(new_val)`
`  `
`                    block[n_block] = str_replace(block[n_block], 15-k, new_val)`
`                    print(block)`
`                print 'FOUND valid ciphertext:', ciphertext`
`                break`
`            r.close()`
`        print 'Moving to previous bytes...'`
`  `
`    print 'Flipping to desired plaintext...'`
`    block[n_block] = xor(block[n_block], '\x10'*16)`
`    block[n_block] = xor(block[n_block], target[n_block])`
`  `
`print 'Final ciphertext:', ''.join(block).encode('hex')`
`  `
`#picoCTF{0r4cl3s_c4n_l34k_6412acff}`