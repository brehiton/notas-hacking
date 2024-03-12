## Objetivo
Using a Secure Shell (SSH) is going to be pretty important.Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `63095` to get the flag?You'll also need the password `f3b61b38`. If asked, accept the fingerprint with `yes`.If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/)If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)
## Pistas
[https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh)

You can try logging in 'as' someone with `<user>`@titan.picoctf.net

How could you specify the port?

Remember, passwords are hidden when typed into the shel
## Solucion
```
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/Cryptography/C3]
└─$ ssh ctf-player@titan.picoctf.net -p 63095                  
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_3e293eea}
Connection to titan.picoctf.net closed.
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/Cryptography/C3]
└─$ 

```
## Notas adicionales 
entre con al ssh con el usuario **ssh ctf-player@titan.picoctf.net -p 63095** y despues la contraseña: f3b61b38
## Referencias 