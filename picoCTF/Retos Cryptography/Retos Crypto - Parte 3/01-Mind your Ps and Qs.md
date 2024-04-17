## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/3cfeb09681369c26e3f19d886bc1e5d9/values)
## Pistas
Bits are expensive, I used only a little bit over 100 to save money
## Solucion
```
Decrypt my super sick RSA:
c: 8533139361076999596208540806559574687666062896040360148742851107661304651861689
n: 769457290801263793712740792519696786147248001937382943813345728685422050738403253
e: 65537 






┌──(hectorr㉿kali2024)-[~/picoCTF/Cryptography/Mind your Ps and Qs]
└─$ python3       
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> p = 1617549722683965197900599011412144490161
>>> q =  475693130177488446807040098678772442581573
>>> n = p * q
>>> n
769457290801263793712740792519696786147248001937382943813345728685422050738403253
>>> tn (p-1)*(q-1)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'tn' is not defined. Did you mean: 'n'?
>>> tn = (p-1)*(q-1)
>>> tn
769457290801263793712740792519696786146770691257482771401340787987731866151331520
>>> e = 65537
>>> d = pow(e, -1. tn)
  File "<stdin>", line 1
    d = pow(e, -1. tn)
               ^^^^^^
SyntaxError: invalid syntax. Perhaps you forgot a comma?
>>> d = pow(e, -1, tn)
>>> m = pow(c, d, n)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'c' is not defined
>>> c = 8533139361076999596208540806559574687666062896040360148742851107661304651861689
>>> m = pow(c, d, n)
>>> m
13016382529449106065927291425342535437996222135352905256639629442503647501498237
>>> bytes.fromhex(hex (m)[2:] )
b'picoCTF{sma11_N_n0_g0od_45369387}'

picoCTF{sma11_N_n0_g0od_45369387}
```
## Notas adicionales 
hicimos el uso de la pagina para saber cual seria el p y q factorizamos el inciso n
## Referencias 
http://factordb.com/index.php?query=769457290801263793712740792519696786147248001937382943813345728685422050738403253