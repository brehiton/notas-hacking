## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Additional details will be available after launching your challenge instance.
## Pistas

## Solucion
```
python3 exploit2.py
[+] Opening connection to saturn.picoctf.net on port 55690: Done
/home/hectorr/picoCTF/tercerParcial/Parte_1_Retos_Crypto/SRA/exploit2.py:26: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/hectorr/picoCTF/tercerParcial/Parte_1_Retos_Crypto/SRA/exploit2.py:29: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 13068456334448152418819269086116564373677011795419126459058050585099699111844
d= 82349400930091365785903068193739454783715142630816091661998647978392668324097
/home/hectorr/picoCTF/tercerParcial/Parte_1_Retos_Crypto/SRA/exploit2.py:33: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Give me the divisors of  5396932688755397839510729380213102648160339302595794199252405392559920303956345088
[2, 2, 2, 2, 2, 2, 2, 2, 3, 3, 3, 3, 17, 23, 43, 47, 1213, 1259, 2060687, 3726095897, 23942758171, 1557705781118453, 753124447075414783436437]
{288306125915103833330958463112215132513, 236426757100220679913005080051703067777, 195578553404478267656430071883467497217, 297947134926013726463817008304907324589, 257216182336108644513305386831092584857, 176597414012810524741997943679924062097, 322185637767303954524077465801551850369, 266281951899670841295881749806795278713, 264852202164114805149941084011597366177, 247096851686587070436631840088776305409, 240136057859158438314481775548131801409, 281788891552004639202644462565008485969, 309418758384581295483545201943980525119, 207707476285269325999858679519219741953, 290722436783120196520933572272879062993}
1b4h2Du0pt8Wf1gi
/home/hectorr/picoCTF/tercerParcial/Parte_1_Retos_Crypto/SRA/exploit2.py:61: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> 1b4h2Du0pt8Wf1gi\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_0795e891}\r\n'
1b4h2Du0pt8Wf1gi
[*] Closed connection to saturn.picoctf.net port 55690

picoCTF{7h053_51n5_4r3_n0_m0r3_0795e891}
```
## Notas adicionales 
hicimos un scrip para resolver este ejercicio era parecido al RSA, visitamos la siguiente pagina para que nos diera lo ultimo del reto lo pusimo entre parentesis []
## Referencias 
https://www.dcode.fr/prime-factors-decomposition