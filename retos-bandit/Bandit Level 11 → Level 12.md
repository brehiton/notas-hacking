## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
## Datos de acceso al nivel
bandit11@bandit.labs.overthewire.org -p 2220
contraseña del otro nivel: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
## Solucion
```
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
```

###### otra solucion
```
bandit11@bandit:~$ python3
Python 3.10.12 (main, Jun 11 2023, 05:26:28) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import codecs
>>> cadena = open("data.txt").read()
>>> codecs.decode(cadena,"rot13")
'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv\n'
>>
```
## Notas adicionales 
aprendi a utilizar el comando 
tr - que es decodificar texto
pero debemos de tener y especificar con corchetes que letras cambiar por ejemplo "[a-zA-Z]" y "[n-za-mN-ZA-M]"
## Referencias 
https://en.wikipedia.org/wiki/Rot13
