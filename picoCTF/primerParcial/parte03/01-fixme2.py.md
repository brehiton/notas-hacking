## Objetivo
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/6/fixme2.py)
## Pistas
Are equality and assignment the same symbol?
## Solucion
```
┌──(hectorr㉿kali2024)-[~]
└─$ nano fixme2.py                         
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3 fixme2.py
  File "/home/hectorr/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ nano fixme2.py   
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3 fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
```
## Notas adicionales 
primero lo ejecutamos y vimos que linea era la del error y era por que para saber si es igual no es con **=** es con ** == **
## Referencias 