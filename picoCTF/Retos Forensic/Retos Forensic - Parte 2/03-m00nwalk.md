## Objetivo
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.
## Pistas
How did pictures from the moon landing get sent back to Earth?

What is the CMU mascot?, that might help select a RX option
## Solucion
```
──(hectorr㉿kali2024)-[~]
└─$ sstv -d message.wav -o result.png

picoCTF{beep_boop_im_in_space}
```
## Notas adicionales 
hicimos el uso de sstv para que el audio que estaba no la tradujiera a imagen png
## Referencias 
https://en.wikipedia.org/wiki/Apollo_11_missing_tapes
https://github.com/colaclanth/sstv