## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once
## Datos de acceso al nivel
bandit8@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: TESKZC0XvTetK0S9xNwm25STk5iWrBvP
## Solucion
```
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc data.txt
 1001  1001 33033 data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$
```
## Notas adicionales 
uniq -u  - nos muestra la linea unica 
sort - orden lineas de texto
c - cuenta las ocurrencias
-u muestra solo lineas unicas
## Referencias 
