## Objetivo
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/241/atbash.jpg).
## Pistas
Download the image and try to extract it.
## Solucion
```
┌──(hectorr㉿kali2024)-[~/picoCTF/Cryptography/HideToSee]
└─$ ls                       
atbash.jpg
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Cryptography/HideToSee]
└─$ steghide -extract -sf atbash.jpg   
steghide: unknown command "-extract".
steghide: type "steghide --help" for help.
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Cryptography/HideToSee]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Cryptography/HideToSee]
└─$ ls             
atbash.jpg  encrypted.txt
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Cryptography/HideToSee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_7142uwv9}


picoCTF{atbash_crack_7142fde9}
```
## Notas adicionales 
hicimos el uso de la herramienta **steghide** y exatrajemos un mensaje que traia entonces le hicimos un cat y no dio la bandera pero encriptada con at bash cipher que lo desencriptamos con la url siguiente
## Referencias 
https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfNzE0MnV3djl9