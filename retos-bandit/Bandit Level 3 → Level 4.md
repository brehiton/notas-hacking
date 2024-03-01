## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.
## Datos de acceso al nivel
bandit3@bandit.labs.overthewire.org -p 2220
utilizamos la anterior contraseña del nivel: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
## Solucion
```
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cat inhere/
cat: inhere/: Is a directory
bandit3@bandit:~$ cat inhere/.hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

otra solucion
```
bandit3@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root 4096 Oct  5 06:19 .
drwxr-xr-x 70 root root 4096 Oct  5 06:20 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
drwxr-xr-x  2 root root 4096 Oct  5 06:19 inhere
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Oct  5 06:19 .
drwxr-xr-x 3 root    root    4096 Oct  5 06:19 ..
-rw-r----- 1 bandit4 bandit3   33 Oct  5 06:19 .hidden
bandit3@bandit:~/inhere$
```
## Notas adicionales 
entre con ls y puse tabulador con el cat pero, me falto entrar a otro archivo que mas abajo le puse tabulador y me lo autocompleto y me salio la contraseña
ls -la nos muestra archivos ocultos de una carpeta 
## Referencias 