## Objetivo
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/2/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/2/codebook.txt)
## Pistas
On the webshell, use `ls` to see if both files are in the directory you are in

The `str_xor` function does not need to be reverse engineered for this challenge.

## Solucion
```
 wget https://artifacts.picoctf.net/c/2/code.py
--2024-03-01 13:10:33--  https://artifacts.picoctf.net/c/2/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: ‘code.py’

code.py                  100%[===============================>]   1.25K  --.-KB/s    in 0.001s  

2024-03-01 13:10:33 (2.25 MB/s) - ‘code.py’ saved [1278/1278]

                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ wget https://artifacts.picoctf.net/c/2/codebook.txt
--2024-03-01 13:10:52--  https://artifacts.picoctf.net/c/2/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.100, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: ‘codebook.txt’

codebook.txt             100%[===============================>]      27  --.-KB/s    in 0s      

2024-03-01 13:10:53 (12.2 MB/s) - ‘codebook.txt’ saved [27/27]

                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ ls
Addadshashanammu      Desktop    Downloads  Pictures  Templates  code.py
Addadshashanammu.zip  Documents  Music      Public    Videos     codebook.txt
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python code.py
picoCTF{c0d3b00k_455157_7d102d7a}
```
## Notas adicionales 
nomas ejecute el archivo code.py con python y me dio la bandera
## Referencias 