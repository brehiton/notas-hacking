## Objetivo
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.
## Pistas
What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)
## Solucion
```
┌──(hectorr㉿kali2024)-[~]
└─$ nc jupiter.challenges.picoctf.org 7480 | grep pico 
picoCTF{digital_plumb3r_06e9d954}

```
## Notas adicionales 
hicimos el uso de | grep entonces le pusimos la palabra que buscara ejemplo:
**| grep pico** 
## Referencias 