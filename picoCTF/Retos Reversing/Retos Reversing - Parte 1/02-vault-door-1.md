## Objetivo
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/29b91e638ccbd76aaa8c0462d1c64d8d/VaultDoor1.java)
## Pistas
Look up the charAt() method online.
## Solucion
```
┌──(hectorr㉿kali2024)-[~/picoCTF/Reversing/vault-door-1]
└─$ cat flag | sort | awk '{print($3)}' | tr -d "'" | tr -d "\n"
d35cr4mbl3_tH3_cH4r4cT3r5_ff63b0                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Reversing/vault-door-1]
└─$ ls                         
VaultDoor1.java  flag
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Reversing/vault-door-1]
└─$ java VaultDoor1.java       
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: d35cr4mbl3_tH3_cH4r4cT3r5_ff63b0
Access denied!

picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_ff63b0}
```
## Notas adicionales 
creamos un archivo y le quitamos y lo ordenamos como debe de ser la bandera
## Referencias 