## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## Datos de acceso al nivel
bandit2@bandit.labs.overthewire.org -p 2220
contraeña del anterior nivel: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
## Solucion
```
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
## Notas adicionales 
primero puse cat y nomas puse tabulador despues de una letra y se me autocompleto y si el nombre es con espacios debo de poner las diagonales para poder entrar con el cat
## Referencias 
https://www.google.com/search?q=spaces+in+filename
