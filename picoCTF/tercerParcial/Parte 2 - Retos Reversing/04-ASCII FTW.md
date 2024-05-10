## Objetivo
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/507/asciiftw).
## Pistas
The combined range of hex-ascii for English alphabets and numerical digits is from 30 to 7A.

Online hex-ascii converters can be helpful.
## Solucion
```
picoCTF{ASCII_IS_EASY_7BCD971D}
```
## Notas adicionales 
hicimos el uso de ghidra para ver el codigo y asi saber donde esta la parte hexadecimal despues vimos que 0x70 eran hexadeciamales copiamos y pegamos en converson de hexadecimal
## Referencias 
https://www.rapidtables.com/convert/number/hex-to-ascii.html