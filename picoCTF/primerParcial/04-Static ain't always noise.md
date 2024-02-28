## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static)? This [BASH script](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh) might help!
## Pistas

## Solucion
'''
brehiton2-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static
--2024-02-27 19:14:09--  https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                                          100%[======================================================================================================>]   8.18K  --.-KB/s    in 0s      

2024-02-27 19:14:09 (248 MB/s) - 'static' saved [8376/8376]

brehiton2-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh
--2024-02-27 19:14:28--  https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                                        100%[======================================================================================================>]     785  --.-KB/s    in 0s      

2024-02-27 19:14:28 (136 MB/s) - 'ltdis.sh' saved [785/785]

brehiton2-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_f6c48608}
brehiton2-picoctf@webshell:~$

picoCTF{d15a5m_t34s3r_f6c48608}

'''
## Notas adicionales 
utilizamos un strinegs mas el nombre del archivo con | y con un grep pico hace una busqueda y un cuentra el picoCTF Ejemplo: **strings static | grep pico**
## Referencias 