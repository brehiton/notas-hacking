## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Datos de acceso al nivel
bandit10@bandit.labs.overthewire.org -p 2220
contraseña del otro nivel: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
## Solucion
bandit10@bandit:~$ base64 data.txt -d -i -w
base64: option requires an argument -- 'w'
Try 'base64 --help' for more information.
bandit10@bandit:~$ base64 data.txt --d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$

##### otra solucion
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

###### otra solucion
bandit10@bandit:~$ python3
Python 3.10.12 (main, Jun 11 2023, 05:26:28) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> cadena = open("data.txt").read()
>>> base64.b64decode(cadena)
b'The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM\n'
>>>
## Notas adicionales 
base64 - utiliza codigo binario a texto de 64 caracteres
-d -decodifica el texto obtenido
## Referencias 
https://en.wikipedia.org/wiki/Base64