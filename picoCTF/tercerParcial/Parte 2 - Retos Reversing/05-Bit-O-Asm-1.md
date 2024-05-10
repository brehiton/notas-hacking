## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).
## Pistas
As with most assembly, there is a lot of noise in the instruction dump. Find the one line that pertains to this question and don't second guess yourself!
## Solucion
```
┌──(hectorr㉿kali2024)-[~/picoCTF/tercerParcial/Parte_2_Retos_reversing/Bit-O-Asm-1]
└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2024-05-10 01:03:05--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.61, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 209 [application/octet-stream]
Saving to: ‘disassembler-dump0_a.txt’

disassembler-dump0_a.txt                  100%[====================================================================================>]     209  --.-KB/s    in 0s      

2024-05-10 01:03:06 (2.75 MB/s) - ‘disassembler-dump0_a.txt’ saved [209/209]

                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/tercerParcial/Parte_2_Retos_reversing/Bit-O-Asm-1]
└─$ ls
disassembler-dump0_a.txt
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/tercerParcial/Parte_2_Retos_reversing/Bit-O-Asm-1]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/tercerParcial/Parte_2_Retos_reversing/Bit-O-Asm-1]
└─$ cat disassembler-dump0_a.txt | grep "eax"
<+15>:    mov    eax,0x30
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/tercerParcial/Parte_2_Retos_reversing/Bit-O-Asm-1]
└─$ python3                  
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x30",16))
48
picoCTF{48}
```
## Notas adicionales 
nomas buscamos el hexadecimal y lo convertimos a entero y fue todo
## Referencias 