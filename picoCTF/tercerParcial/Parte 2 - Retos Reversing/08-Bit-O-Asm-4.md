## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).
## Pistas
Don't tell anyone I told you this, but you can solve this problem without understanding the compare/jump relationship.

Of course, if you're really good, you'll only need one attempt to solve this problem.
## Solucion
```
This is what CPU executes:

<+15>:  Store 0x9fe1a in mem pointer by [rbp-0x4]
<+22>:  Compare [rbp-0x4] and 0x2710
<+29>:  Jump to instruction at <+37> if [rbp-0x4] is less or equeal to 0x2710 (it is NOT)
<+31>:  Substract 0x65 from [rbp-0x4] and store it in [rbp-0x4]
<+35>:  Jump to <+41>
<+37>:  [NOT EXECUTED]
<+41>:  Store value pointed by [rbp-0x4] in eax register

After all computations and conversion from hex, we get the decimal number and our flag:
picoCTF{654773}
```
## Notas adicionales 
tambien hicimos operaciones
## Referencias 