## Objetivo
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
## Pistas
How do operating systems know what kind of file it is? (It's not just the ending!

Make sure to submit the flag as picoCTF{XXXXX}
## Solucion
```
picoCTF{now_you_know_about_extensions}
```
## Notas adicionales 
hicimos el uso del comando **xxd mas el archivo | head** para saber que firma tenia y vimos que era png
entonces hicimos el uso de mv para cambiarle el formato a png y fue todo
## Referencias 
https://en.wikipedia.org/wiki/File_format
https://en.wikipedia.org/wiki/List_of_file_signatures/