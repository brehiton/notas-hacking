
## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
## Datos de acceso al nivel
bandit16@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: JQttfApK4SeyHwDlI9SXGR50qclOAil1
## Solucion
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 20 17:50:06 2024 GMT; NotAfter: Feb 20 17:51:06 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEQ9wEgDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTc1MDA2WhcNMjQwMjIwMTc1MTA2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDA
gdd50zQdwKnADuCYAoUSFvGreD2Mr/e6QZK+31XsKXCd/+cGHdmkqerggVlwno8T
3lmAaRw+Pk/nNdn3xJEGGq5guV2YhAnT+IQgP6+76ii/4gUCQxnaTtmslJDSfv7i
km+qYsFRL1YdtOo5od2etkLdorXGqGcIrB6ilCgKgQ2Q7FqMjh7n37HPk8yaWCwX
M/JZ7jkXw4mf2Un9UILgo/oJfR0JhMq6cDkHztG0E6j5ruknDeeOMGimH9pmzaa9
xdJe1GTtk+v03FIng0IfHi0HVPUCN8dl9rKLzn/LKZ3UftyffIErE7nDCLaGpVBK
DQzkq5gMPShGa1RT7nkFAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBh
XmVUELbEPhoHaMrhwHyd24bRzYiiOemi75OA6QywOLh7moC8MGKvtI0mHhhA+lfB
eEvOOPwL5om4culG+KnC24fdWzwX/PPtkYKocNSrIQINrVhTwBbGwnC+WCSYizZS
43Zav+szrJ6H66qO4x4wXU9p1qC24dIpY5dfBsy4m8P/XzUtg68YJng1EIuGM6DF
CnMWXUB0cfUgBsbWPMrQlJd5sHifKeglK3kBCXn3zb9T881YbLNAwMK2a5SnPdh8
eTg1e7pdNYwPvHcxYPySGyQCkLpLHduWUxVNrUfsVHrxI6rrHynZ5vv4+ulAmhAc
YoU33/wx/D1oycw1GLHh
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: F03246827894211AC9C85B08DA221F5BB259836D5FC758495F9499E8B8BB2DB9
    Session-ID-ctx:
    Resumption PSK: A49458ED405E4C7B5D7A02FF99D63F0B10B3F000133CC6172DFBC7A155A9EE2A6F28ED16E276CA61D41D579FDDC8820F
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 92 ed 0d d5 75 f9 0c 95-ed 08 73 73 af f3 6c c3   ....u.....ss..l.
    0010 - f5 f4 86 62 39 0d f6 91-1f c1 bc cd a0 e1 ec 61   ...b9..........a
    0020 - e8 58 a2 44 be b4 66 aa-f8 a8 26 a5 51 28 d8 2c   .X.D..f...&.Q(.,
    0030 - 39 1a 4c dc 07 ba d7 ab-01 d0 9e e3 cb a5 f3 2d   9.L............-
    0040 - 50 94 0d 44 77 67 28 8b-70 2d 2a 8f 71 47 09 c2   P..Dwg(.p-*.qG..
    0050 - 5b ed 0c b7 95 45 61 0b-1f 1c 22 b0 2e c7 4c 77   [....Ea..."...Lw
    0060 - c1 9f 29 0b 7d 50 44 73-2b d6 d3 c9 bc 89 93 01   ..).}PDs+.......
    0070 - 16 65 e8 9b b1 c7 82 55-15 cb c2 2f 6c 65 35 0d   .e.....U.../le5.
    0080 - 6d b8 31 4c 4f 41 ab 52-bf 8d 15 f2 9c c2 ef 5d   m.1LOA.R.......]
    0090 - aa 16 6d 14 57 68 cd a2-4d 6f e2 a0 3a a5 5b f5   ..m.Wh..Mo..:.[.
    00a0 - 83 31 53 4c 7f 48 59 e1-ee 34 97 03 f5 57 34 fa   .1SL.HY..4...W4.
    00b0 - 5e 97 52 bb d7 fb 08 1f-97 31 a2 99 ce e1 ba cd   ^.R......1......
    00c0 - d2 83 4a c9 77 b1 9f 43-df 24 e5 85 6e 2c 9d d3   ..J.w..C.$..n,..

    Start Time: 1708478359
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: C61BC62F0DD80451D1F623531E88C7C2805EC2494BE22BFBAB53D44C19A24A88
    Session-ID-ctx:
    Resumption PSK: 706C9617D1215CC73458B4CF428769DDCC864F431EF06D81B7A102BF486602BA403050D12C55EEC922C1336D477239D2
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 92 ed 0d d5 75 f9 0c 95-ed 08 73 73 af f3 6c c3   ....u.....ss..l.
    0010 - 01 b4 71 b9 e2 12 e3 f0-8e 1a 9e d8 ea 9f a1 a1   ..q.............
    0020 - c9 34 db a9 ac 53 77 67-42 e8 8e 06 e4 b9 8b 65   .4...SwgB......e
    0030 - a0 41 7e 76 40 c1 9f c3-26 7e 2a cf 81 13 2a 8f   .A~v@...&~*...*.
    0040 - e2 ec eb f0 3a 30 47 07-f9 7f 65 11 ae 00 be 22   ....:0G...e...."
    0050 - 25 96 81 56 cd 86 fa ef-d5 a3 37 e0 de ea 21 fc   %..V......7...!.
    0060 - 74 50 89 3a a7 91 88 87-03 b2 88 27 d6 c5 c8 43   tP.:.......'...C
    0070 - b2 47 2f 4b 80 32 72 09-54 51 50 49 a3 4e 72 3a   .G/K.2r.TQPI.Nr:
    0080 - 9c 1a b0 a6 81 62 94 52-be f9 4b ec 6b a9 70 f5   .....b.R..K.k.p.
    0090 - 71 38 8b c7 e4 b4 e8 18-32 14 42 35 52 bf e2 e9   q8......2.B5R...
    00a0 - 19 b5 2c 63 79 2a de 7f-97 ff 90 c8 19 83 34 87   ..,cy*........4.
    00b0 - 1f 83 c3 e7 f9 db 14 83-3e 14 2e 6d 40 bb bb 4a   ........>..m@..J
    00c0 - 36 bd 0a cd 78 64 bc 31-89 7d 98 91 d9 4e 7c bc   6...xd.1.}...N|.

    Start Time: 1708478359
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$
## Notas adicionales 
para este ejercicio usamos nmap que es un escaniador de puertos que nos indica cuales son los que estan abiertos y tambien utilizamos ssl para que nos de la clave es igual como en el otro nivel pero nomas buscamos cual puerto esta abierto con el nmap
## Referencias 
https://en.wikipedia.org/wiki/Port_scanner