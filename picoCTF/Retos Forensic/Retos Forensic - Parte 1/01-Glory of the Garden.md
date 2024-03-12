## Objetivo
This [garden](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contains more than it seems.
## Pistas
What is a hex editor?
## Solucion
```
picoCTF{more_than_m33ts_the_3y3657BaB2C}
```
## Otra solucion
```
┌──(hectorr㉿kali2024)-[~/Forensic]
└─$ strings garden.jpg | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y3657BaB2C}"
```
## Notas adicionales 
hicimos el uso del comando **hexeditor** mas el archivo y vemos el editor utilizamos el comando 
**CTRL + w** para poder escribir la palabra y escribimos pico y le damos en buscar y nos da la bandera.

hicimos el uso de **strings garden.jpg | grep pico**
para que nos diera la bandera 
## Referencias 