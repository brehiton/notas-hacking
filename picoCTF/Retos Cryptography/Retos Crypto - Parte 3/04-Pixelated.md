## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled2.png)
## Pistas
[https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)

Think of different ways you can "stack" images
## Solucion
```
┌──(hectorr㉿kali2024)-[~/picoCTF/Cryptography/Pixelated]
└─$ ls 
scrambled1.png  scrambled2.png
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Cryptography/Pixelated]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite flga.png
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Cryptography/Pixelated]
└─$ open flga.png 

picoCTF{da8fcef8}
```
## Notas adicionales 
hicimos el uso de la herramienta **imagemagick** 
## Referencias 