## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
## Datos de acceso al nivel
bandit9@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
## Solucion
```
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ file data.txt
data.txt: data
bandit9@bandit:~$ strings data.txt | grep ==
x]T========== theG)"
========== passwordk^
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
```
## Notas adicionales 
strings - muestra las cadenas dentro de un archivo binario o de datos.
## Referencias 
