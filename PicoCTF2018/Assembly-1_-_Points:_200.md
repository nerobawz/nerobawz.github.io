[Category:Picoctf](/Category:Picoctf "wikilink")

`What does asm1(0x15e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. Source located in the directory at /problems/assembly-1_3_cfc4373d0e723e491f368e7bcc26920a. `

`.intel_syntax noprefix`
`.bits 32`
`.global asm1`
`asm1:`
`       push    ebp`
`       mov ebp,esp`
`       cmp DWORD PTR [ebp+0x8],0xdc`
`       jg  part_a  `
`       cmp DWORD PTR [ebp+0x8],0x8`
`       jne part_b`
`       mov eax,DWORD PTR [ebp+0x8]`
`       add eax,0x3`
`       jmp part_d`
`part_a:`
`       cmp DWORD PTR [ebp+0x8],0x68`
`       jne part_c`
`       mov eax,DWORD PTR [ebp+0x8]`
`       sub eax,0x3`
`       jmp part_d`
`part_b:`
`       mov eax,DWORD PTR [ebp+0x8]`
`       sub eax,0x3`
`       jmp part_d`
`       cmp DWORD PTR [ebp+0x8],0xfc`
`       jne part_c`
`       mov eax,DWORD PTR [ebp+0x8]`
`       sub eax,0x3`
`       jmp part_d`
`part_c:`
`       mov eax,DWORD PTR [ebp+0x8]`
`       add eax,0x3`
`part_d:`
`       pop ebp`
`       ret`