## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.
## Pistas
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solucion
```
wget https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
--2024-03-01 13:22:40--  https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: ‘file’

file                     100%[===============================>]  14.21K  --.-KB/s    in 0s      

2024-03-01 13:22:41 (138 MB/s) - ‘file’ saved [14551/14551]

                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ ls
Addadshashanammu      Desktop    Downloads  Pictures  Templates  code.py       convertme.py
Addadshashanammu.zip  Documents  Music      Public    Videos     codebook.txt  file
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ strings file | grep pico                 
picoCTF{grep_is_good_to_find_things_dba08a45}
```
## Notas adicionales 
utilizamos el uso de grep, pero como en los problemas anteriores primero pusimos a strings el nombre del archivo mas la barrita | mas el grep y lo que queremos buscar por ejemplo:
**strings file | grep pico**

## Referencias 