## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**
## Datos de acceso al nivel
bandit7@bandit.labs.overthewire.org -p 2220
contraseña anterior del nivel: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solucion
```
bandit7@bandit:~$ wc data.txt
  98567  197133 4184396 data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$
```
## Notas adicionales 
-head muestras las primeras lineas de un archivo
-tail - muestra las ultimas lineas de un archivo
-ws - cuenta las lineas de un archivo
-grep - filtra lineas en base a un patron

## Referencias 