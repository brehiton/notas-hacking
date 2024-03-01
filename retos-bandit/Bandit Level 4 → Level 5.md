## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.
## Datos de acceso al nivel
bandit4@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
## Solucion
```
bandit4@bandit:~/inhere$ cat ./*
QRrtZi      H|ȧ^7L3Yͯ   ŴEYܚ   V&hFO̫`\-⃐Hx2Kix#e>VOp{   MUb4gQeE}:gj8<.e��Se 0]7b<~G=1��B׃"9ؽ5lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
K~+9"T*Z$"r
Z\жq7��/nbandit4@bandit:~/inhere$
```
## Notas adicionales 
utilice el comando de cat ./* que agarra todos los archivos y nos muestra la contraseña
tambien aprendi que con el comando reset tambien resetea la consola es como si la limpiara
el asteristico es un comodin que nos agarra todos los archivos.
## Referencias 