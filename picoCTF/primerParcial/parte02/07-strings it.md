## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?
## Pistas
[strings](https://linux.die.net/man/1/strings)
## Solucion
```
──(hectorr㉿kali2024)-[~]
└─$ strings string | grep pico
strings: 'string': No such file
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ ls
Addadshashanammu      Documents  Pictures   Videos        convertme.py  strings
Addadshashanammu.zip  Downloads  Public     code.py       file
Desktop               Music      Templates  codebook.txt  fixme1.py
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ strings strings | grep pico
picoCTF{5tRIng5_1T_827aee91}

```
## Notas adicionales 
otra vez utilizamos el grep, en este caso quedo asi: **strings strings | grep pico**
## Referencias 