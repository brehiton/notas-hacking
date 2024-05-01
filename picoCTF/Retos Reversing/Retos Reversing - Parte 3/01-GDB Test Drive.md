## Objetivo
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/87/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
## Pistas

## Solucion
```
picoCTF{d3bugg3r_dr1v3_7776d758}
```
## Notas adicionales 
nomas seguimos las instrucciones
## Referencias 