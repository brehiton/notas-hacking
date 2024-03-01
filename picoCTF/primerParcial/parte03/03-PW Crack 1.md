## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.
## Pistas
To view the file in the webshell, do: `$ nano level1.py`

To exit `nano`, press Ctrl and x and follow the on-screen prompts.

The `str_xor` function does not need to be reverse engineered for this challenge.
## Solucion
```
──(hectorr㉿kali2024)-[~]
└─$ nano level1.py   
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3 level1.py 
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}

```
## Notas adicionales 
lo que fue es de que entramos a ver el codigo vimos que contraseña necesitaba la copiamos y pegamos
## Referencias 