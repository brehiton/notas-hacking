## Objetivo
Oracles can be your best friend, they will decrypt anything, except the flag's ciphertext. How will you break it? Connect with `nc mercury.picoctf.net 33780`.
## Pistas
What can you do with a different pair of ciphertext and plaintext? What if it is not so different after all...
## Solucion
```
from pwn import *
import binascii
r = remote("mercury.picoctf.net", 33780)
print(r.recvuntil("n:"))
n = int(r.recvline())
print(n)
print(r.recvuntil("e:"))
e = int(r.recvline())
print(e)
print(r.recvuntil("ciphertext:"))
c = int(r.recvline())
print(c)
print(r.recvuntil("to decrypt:"))

r.sendline(str(pow(2,e,n)*c))
print(r.recvuntil("you go:"))
p2 = int(r.recvline())
print(p2)
print(p2//2)
st="{:x}".format(p2//2)
print(binascii.unhexlify(st))


picoCTF{m4yb3_Th0se_m3s54g3s_4r3_difurrent_0801973}
```
## Notas adicionales 
creamos un exploit en python ejecutamos y listo
## Referencias 