## Objetivo
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.
## Pistas
I hear python can convert things.

It might help to have multiple windows open.
## Solucion
```
─(hectorr㉿kali2024)-[~]
└─$ nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
colorado
Please give the 01100011 01101111 01101100 01101111 01110010 01100001 01100100 01101111 as a word.
...
you have 45 seconds.....

Input:
colorado
Please give me the  163 154 165 144 147 145 as a word.
Input:
sludge
Please give me the 74657374 as a word.
Input:
test
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}
```
## Notas adicionales 
primero ponemos el texto que nos indica y es **colorado**, despues nos da tipo de numero octal, entonces buscamos una pagina que convierta de octal a texto, despues nos da un numero hexadecimal y lo tenemos que convertir a texto entonces visitamos la pagina de hex to text.
## Referencias 
https://v2.cryptii.com/octal/text
https://www.rapidtables.com/convert/number/hex-to-ascii.html