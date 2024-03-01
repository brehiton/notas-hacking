## Objetivo
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 49700`
## Pistas
ASCII is one of the most common encodings used in programming

We know that the glitch output is valid Python, somehow!

Press Ctrl and c on your keyboard to close your connection and return to the command prompt.
## Solucion
```
┌──(hectorr㉿kali2024)-[~]
└─$ nc saturn.picoctf.net 49700            
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
                                                                                                 
┌──(hectorr㉿kali2024)-[~]
└─$ python3          
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
'picoCTF{gl17ch_m3_n07_a4392d2e}'
>>> 
KeyboardInterrupt
>>> exit()

```
## Notas adicionales 
ejecutamos el nc pero habia un error **chr(0x34)** estos caracteres eran el problema lo que hicimos fue copiar todo el texto que nos dio y abrir python3 y pegarlo y no lo dio
## Referencias 