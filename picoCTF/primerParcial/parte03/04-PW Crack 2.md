## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.
## Pistas
The `str_xor` function does not need to be reverse engineered for this challenge.
## Solucion
```
(hectorr㉿kali2024)-[~]
└─$ python3 level2.py
Please enter correct password for flag: ^CTraceback (most recent call last):
  File "/home/hectorr/level2.py", line 27, in <module>
    level_2_pw_check()
  File "/home/hectorr/level2.py", line 17, in level_2_pw_check
    user_pw = input("Please enter correct password for flag: ")
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
KeyboardInterrupt

                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ nano level2.py   
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3          
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
'4ec9'
>>> 
KeyboardInterrupt
>>> exit()
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3 level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}

```
## Notas adicionales 
vimos el codigo con nano level2.py y vimos que la contraseña estaba con los mismo signos raros **chr(0x34)**.
abrimos python y pegamos todos los signos raros y asi nos dio bien lo que queria decir y ejecutamos con python3 level2.py y nos pidio la contraseña y lo que nos dio los signos raros esa era la contraseña
## Referencias 