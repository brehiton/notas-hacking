## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Pistas
To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`

To exit `bvi` type `:q` and press enter.

The `str_xor` function does not need to be reverse engineered for this challenge.
## Solucion
```
┌──(hectorr㉿kali2024)-[~]
└─$ nano level3.py     
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3 level3.py                                      
Please enter correct password for flag: 8799
That password is incorrect
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3 level3.py  
Please enter correct password for flag: d3ab
That password is incorrect
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3 level3.py
Please enter correct password for flag: 1ea2
That password is incorrect
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3 level3.py
Please enter correct password for flag: acaf
That password is incorrect
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3 level3.py
Please enter correct password for flag: 2295
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_6f98a49f}

```
## Notas adicionales 
lo que hicimos fue revisar bien el codigo de level3.py y hasta abajo venian varias contraseñas 7 como dice el problema entonces anduvimos de aprueba y error, para ello abrimos dos terminales para que fuese poco el tiempo
## Referencias 