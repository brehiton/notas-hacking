## Objetivo
I wonder what this really is... [enc](https://mercury.picoctf.net/static/dd6004f51362ff76f98cb8c699510f23/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`
## Pistas
You may find some decoders online
## Solucion
```
picoCTF{16_bits_inst34d_of_8_0ddcd97a}
```
## Notas adicionales 
le hicimos un cat al archivo y despues visitamos al ciberchef con la herramineta magic lo solucionamos
## Referencias 
https://gchq.github.io/CyberChef/#recipe=Magic(3,false,false,'')&input=54Gp5o2v5I2U5Jm744S25b2i5qW0542f5qWu542044y05pGf5r2m5by45byw5pGk5o2k46S35oW9