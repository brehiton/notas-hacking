## Objetivo
Morse code is well known. Can you decrypt this?Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav).Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.
## Pistas
Audacity is a really good program to analyze morse code audio.
## Solucion
```
picoCTF{WH47_H47H_90D_W20U9H7}
```
## Notas adicionales 
utilizamos el powershell de windows para hacer esta operacion con el comando **Invoke-WebRequest -Uri https://artifacts.picoctf.net/c/79/morse_chal.wav -OutFile archivo.wav** descargamos archivos es igual como el wget de linux y utilizamos esta pagina para decodificar el audio
## Referencias 
https://morsecode.world/international/decoder/audio-decoder-adaptive.html