## Objetivo
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/fe16c756149cfa85f23e73cd9dbd6a25/Addadshashanammu.zip)
## Pistas
After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...
## Solucion
```
┌──(hectorr㉿kali2024)-[~]
└─$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku 
                                                                                                                                                              
┌──(hectorr㉿kali2024)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls 
fang-of-haynekhtnamet
                                                                                                                                                              
┌──(hectorr㉿kali2024)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ cat fang-of-haynekhtnamet                                                                                
 HH/lib64/ld-linux-x86-64.so.2GNUGNU_���
8#TT 1tt$D���o�N
�� ��0)@▒=      (;▒�                                                                                                                                                              .so.6puts__cxa_finalize__libc_start_mainGLIBC_2.2.5_ITM_deregisterTMCloneTable__gmon_start___ITM_registerTMCloneTableu▒i    1�
┌──(hectorr㉿kali2024)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=5fffe70019957f0a27a70bb886b2cfb9f9b21d6e, not stripped
                                                                                                                                                              
┌──(hectorr㉿kali2024)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ strings fang-of-haynekhtnamet | grep pico
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_76266e38}


picoCTF{l3v3l_up!_t4k3_4_r35t!_76266e38}
```
## Notas adicionales 
tabulador y lo que nos enseño el profe de strings mas el archivo con la barra | y grep con el nombre que queremos buscar **strings fang-of-haynekhtnamet | grep pico**
## Referencias 