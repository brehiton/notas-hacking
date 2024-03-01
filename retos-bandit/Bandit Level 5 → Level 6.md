## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
## Datos de acceso al nivel
bandit5@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
## Solucion
```
bandit5@bandit:~/inhere$ man find
bandit5@bandit:~/inhere$ bandit5@bandit:~/inhere$ find . -readable -size 1033c -type f
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Notas adicionales 
find es un comando poderoso y permite buscar archivos y si le pongo 
-readable nos muestra archivos legibles
size . el tamaño del archivo (c para bytes)
-type .el tipo de archivo
## Referencias 
le puse man al find 