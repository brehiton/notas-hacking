## Objetivo
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:53554/](http://mercury.picoctf.net:53554/)
## Pistas
Maybe you have more than 2 choices

Check out tools like Burpsuite to modify your requests and look at the responses
## Solucion
```
picoCTF{r3j3ct_th3_du4l1ty_2e5ba39f}
```
## Otra solución
```
──(hectorr㉿kali2024)-[~]
└─$ curl -I http://mercury.picoctf.net:53554/index.php?                                                      
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_2e5ba39f}
Content-type: text/html; charset=UTF-8

                                                                                                                                                              
┌──(hectorr㉿kali2024)-[~]
└─$ 

```
## Notas adicionales 
el -I hace referencia como si pusieramos HEAD
## Referencias 
https://developer.mozilla.org/es/docs/Web/HTTP/Methods
https://www.techtarget.com/searchitchannel/definition/proxy-hacking