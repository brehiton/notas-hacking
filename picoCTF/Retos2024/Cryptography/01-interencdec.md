## Objetivo
Can you get the real meaning from this file.Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).
## Pistas
Engaging in various decoding processes is of utmost importance
## Solucion
```
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024]
└─$ ls
enc_flag
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024]
└─$ cat enc_flag 
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024]
└─$ base64 enc_flag --d                                                                
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='
                                                                                                                                                                      
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024]
└─$ nano reto1          
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024]
└─$ base64 reto1       
ZDNCcWRrcEJUWHRxYUd4NmFIbGZhek5xZVRsM1lUTnJYMmcwTjJvMmF6WTVmUT09Cgo=
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024]
└─$ ls
enc_flag  reto1
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024]
└─$ base64 reto1 -d
wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024]
└─$ 

picoCTF{caesar_d3cr9pt3d_a47c6d69}
```
## Notas adicionales 
primero le hicimos un cat pero vimos que estaba en base64 por los dos **= =** hicimos la decodificacion con **base64 el nombre del archivo -d** y nos dio el texto pero estaba cifrado tambien lo que hicimos fue otro decifrado pero nomas agarrando todo adentro de las comillas y creamos un archivo con nano y ahi pusimos el texto para poderlo descrifrar de nuevo por que estaba otra vez en base64 y nos dio el siguiente texto **wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}** 
utilizamos el rot19 de la pagina cyberchef 
## Referencias 
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,19)&input=d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ