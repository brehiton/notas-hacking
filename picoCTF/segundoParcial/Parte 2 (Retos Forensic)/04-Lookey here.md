## Objetivo
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/124/anthem.flag.txt).
## Pistas
Download the file and search for the flag based on the known prefix.
## Solucion
```
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/Lookey here]
└─$ strings anthem.flag.txt | grep pico
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}

```
## Notas adicionales 

## Referencias 