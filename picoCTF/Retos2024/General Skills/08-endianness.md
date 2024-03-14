## Objetivo
Know of little and big endian?

Additional details will be available after launching your challenge instance.
## Pistas

## Solucion
```
──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills]
└─$ nc titan.picoctf.net 65450
Welcome to the Endian CTF!
You need to find both the little endian and big endian representations of a word.
If you get both correct, you will receive the flag.
Word: ghvvd
Enter the Little Endian representation: 6476766867




^C
                                                                                                                                                                    
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills]
└─$ nc titan.picoctf.net 65450
Welcome to the Endian CTF!
You need to find both the little endian and big endian representations of a word.
If you get both correct, you will receive the flag.
Word: asebq
Enter the Little Endian representation: 7162657361
Correct Little Endian representation!
Enter the Big Endian representation: 6173656271
Correct Big Endian representation!
Congratulations! You found both endian representations correctly!
Your Flag is: picoCTF{3ndi4n_sw4p_su33ess_28329f0a}

```
## Notas adicionales 
primero utilice en convertir el texto que me dio en hexadecimal y luego visite la pagina de big endian para hacer la transferencia de little endian a big endian
## Referencias 
https://www.rapidtables.com/convert/number/ascii-to-hex.html
https://www.save-editor.com/tools/wse_hex.html