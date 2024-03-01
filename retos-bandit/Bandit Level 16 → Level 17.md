
## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
## Datos de acceso al nivel
bandit16@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: JQttfApK4SeyHwDlI9SXGR50qclOAil1
## Solucion
```
bandit16@bandit:~$ nmap -p31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2024-02-22 17:00 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00013s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.87 seconds
bandit16@bandit:~$ openssl s_client-connect localhost:31046
Invalid command 's_client-connect'; type "help" for a list.
bandit16@bandit:~$ openssl s_client-connect localhost:31518
Invalid command 's_client-connect'; type "help" for a list.
bandit16@bandit:~$ openssl s_client -connect localhost:31518
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 17:51:07 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 20 17:51:07 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 20 17:50:07 2024 GMT; NotAfter: Feb 20 17:51:07 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIED6TmQjANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTc1MDA3WhcNMjQwMjIwMTc1MTA3WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDG
ItRI0YQSg7GaQar1vRzAkcuAUsO/ZdTZtFmzkN6TyBt24ZrKKBWpLll6cDGt6+V/
G4w+kQpc3wRpfihFiudZxYahIsEoMvaSS3VsAKP1oeqOk6ya9l4v7wXZE/HnxmT/
N+rB/Fnpqo4Wxbi+nbIJSPU7xmK5BslH6RsJxveZOWmePnzVSkJbFmuj7EcLuYZV
asT1RoEYjkkNRM1+T7729Rv3ZkCF7S7AIV/9RobP+qUGWaweIcSIK73ZZwySaaYU
q087YDcrl+YteXLFJukqBLiDrl2QeBGjKnJ2JcNfGt8lgUDzGR85rZy/bJZuNNKG
2DIe6zfO4Qtd14aS1Hk1AgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQDF
AbYvgfNCh6RFSe1tNefMqhZoywHtMdo2G1WGxGOgbXG0bJkjQ/BEHMeflkVmpv3A
/DoAGLW/ZO1VBgb9HImrYWDWGiXUo+cJxWiLLW9ewP6l1yCpOjPyT9DPUBzlKMdA
FFI3W0ehvIB6vv2YPvLsbgfDKWO+yh1OPZW+DQ0kAbIRiUlbuQrTYdK4mkckaj7h
oJQ93yBr80uGuErR+unKW2Vj0JI4KxglZVH9ekekbTBxNVqMkpnr2n/eEfnmFRuJ
IlAlXbdIC/5Fo0Llk/sERLUQA6FZ5eqykUvVeoJTj9kodi03AkNL2mxDTy1KaW+B
sPf9vsFkDW8mfXcNDFK2
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
    Session-ID: 2F259CFFB930FF43DB375CE96EE715340C70D911E1CD344BB0962AE76229BA90
    Session-ID-ctx:
    Resumption PSK: 5A2489C7B19CF85A2F544B8F9126CF49A18F472DCF03699FA09416EAE2B70FF15D5A62F4B7A2225E9A3441EA898AA2D9
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 67 62 ad 30 72 ef 35 8b-4b 97 68 8c 1c f3 24 79   gb.0r.5.K.h...$y
    0010 - 2b f1 a3 69 e1 c0 b4 cd-79 53 ae c6 14 89 5b 19   +..i....yS....[.
    0020 - 56 81 6d f0 d9 0a d8 d7-0f 83 51 c0 39 9d b5 5d   V.m.......Q.9..]
    0030 - b9 0c 14 4f a1 46 fb bd-39 40 32 dd 90 cc 2d f1   ...O.F..9@2...-.
    0040 - 4a b2 f5 b6 1e 1f e4 97-72 b7 94 fb 58 0d 1f 9c   J.......r...X...
    0050 - fa c4 89 0f 6b 25 6f f2-09 fd 71 53 05 d8 c7 15   ....k%o...qS....
    0060 - fc 3d e0 d2 e2 8e eb 45-d6 dc fb 95 9f 2d b1 81   .=.....E.....-..
    0070 - f8 60 95 85 6c af 59 68-46 b2 c7 79 49 31 74 20   .`..l.YhF..yI1t
    0080 - 33 65 99 6f 89 c7 f3 54-71 3b 22 f0 77 f8 74 bb   3e.o...Tq;".w.t.
    0090 - 37 46 12 5c c0 7d bd 51-ce d9 63 15 94 91 1a 58   7F.\.}.Q..c....X
    00a0 - 84 6f 56 7e 2b 84 aa 3e-67 20 a4 91 ce 48 14 2b   .oV~+..>g ...H.+
    00b0 - 25 1e f7 7e 24 19 af ed-0b e6 43 04 12 ad 3b 4a   %..~$.....C...;J
    00c0 - c4 00 9f df 8c c0 50 0c-13 15 bd 91 50 11 f9 14   ......P.....P...

    Start Time: 1708621442
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
    Session-ID: 6D78DCAD47868DDEA8C9EA0639DEEAC848D1A9F12C62773EB9E2914F4D137BCC
    Session-ID-ctx:
    Resumption PSK: C5B719D7BF5F879ADFDF9142883B5DBFAE495C7E32B71C70B5B4587EED50414DE53C33859F6611A6F4BB8BB78009899B
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 67 62 ad 30 72 ef 35 8b-4b 97 68 8c 1c f3 24 79   gb.0r.5.K.h...$y
    0010 - 94 f5 0e 3a 19 01 46 53-e7 e6 dc e9 c2 e7 58 11   ...:..FS......X.
    0020 - 29 de 4c e5 76 f3 24 6f-da 09 fa 9d cc de ab 24   ).L.v.$o.......$
    0030 - f2 1f b6 1d ba f4 b8 9e-f5 74 14 dc bb eb 7c da   .........t....|.
    0040 - c3 19 67 34 e0 7d c5 17-53 fa 23 65 51 80 86 e3   ..g4.}..S.#eQ...
    0050 - 6c b0 8b f1 c3 20 03 dd-f5 dc 58 52 9d 41 43 b1   l.... ....XR.AC.
    0060 - 35 eb fc d2 9f c4 dc f7-9e 91 09 13 f8 28 41 67   5............(Ag
    0070 - 53 04 db f5 91 e8 f4 8e-1a 0f a8 48 c1 34 18 ef   S..........H.4..
    0080 - 36 78 57 fe fa 94 39 f8-ac be 29 e8 d0 a6 32 25   6xW...9...)...2%
    0090 - 10 7c 10 fc 6b c7 12 27-79 5d eb b2 b2 42 aa fe   .|..k..'y]...B..
    00a0 - 19 81 04 94 b6 b1 e5 3c-82 4b 6d 29 a6 a2 04 9a   .......<.Km)....
    00b0 - 89 16 4a 16 2a ed fa 7d-1e 2f e2 f5 3f 58 3a c7   ..J.*..}./..?X:.
    00c0 - be 39 54 fe 2c 71 36 2d-b6 54 76 99 07 e1 fd ec   .9T.,q6-.Tv.....

    Start Time: 1708621442
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
JQttfApK4SeyHwDlI9SXGR50qclOAil1
^C
bandit16@bandit:~$ openssl s_client -connect localhost:31691
CONNECTED(00000003)
80DBF0F7FF7F0000:error:0A0000F4:SSL routines:ossl_statem_client_read_transition:unexpected message:../ssl/statem/statem_clnt.c:398:
---
no peer certificate available
---
No client certificate CA names sent
---
SSL handshake has read 293 bytes and written 300 bytes
Verification: OK
---
New, (NONE), Cipher is (NONE)
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 0 (ok)
---
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
    Session-ID: 4EFDE527771817E7F3C6E98D1FDF9E055CE41289E65F5125FA927E16491DED2E
    Session-ID-ctx:
    Resumption PSK: 8D9171E47C52ED3F2F7C76EDA3EA14ADF38E82B19700FC154CF575AA33F6DD7D7996565F67AE8C79C5E19094541375D5
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 92 ed 0d d5 75 f9 0c 95-ed 08 73 73 af f3 6c c3   ....u.....ss..l.
    0010 - 8d 66 cc a8 10 a7 7b 44-1a 8b 1b f1 87 a7 08 b2   .f....{D........
    0020 - fc 11 0c d5 6c ee 40 26-74 1b 17 38 a6 57 37 14   ....l.@&t..8.W7.
    0030 - da 95 ec 3c 2b a7 37 2d-5b d2 90 f4 b0 9c af 26   ...<+.7-[......&
    0040 - 79 01 40 0e ee 93 37 97-df 7c 47 68 10 4d 89 52   y.@...7..|Gh.M.R
    0050 - 51 2c 3d 8c ef e0 75 7b-2e 78 b0 c5 31 5e 65 ac   Q,=...u{.x..1^e.
    0060 - 50 b1 a2 06 9e 79 02 27-d3 54 c0 f7 21 c3 da e8   P....y.'.T..!...
    0070 - e2 6d cd b9 74 79 b8 cc-08 ac dd 9d ec 45 16 ea   .m..ty.......E..
    0080 - fc 80 73 17 54 bf 37 f6-4e 94 33 a3 6d 45 6d 2d   ..s.T.7.N.3.mEm-
    0090 - 7b 0b f7 b9 17 ac 86 e3-4e f9 ad 7c aa 94 81 2d   {.......N..|...-
    00a0 - ed 6b 01 d8 89 9c 4b 0c-e9 11 01 f8 12 a3 85 38   .k....K........8
    00b0 - b9 ed 82 c7 25 84 3c b1-8c c3 0c 30 c0 2f c7 71   ....%.<....0./.q
    00c0 - 25 19 cf 89 77 d6 13 ec-d4 10 38 63 a9 c7 eb 8a   %...w.....8c....

    Start Time: 1708621498
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
    Session-ID: 12C0EFA7AFAA19243D050381FDFE5A3616B0505DD8251CC32720A2DA66E279C3
    Session-ID-ctx:
    Resumption PSK: 6CE874B1770413CCD98DDC4D94F537A4AAA2F7637407DEC624FFE71C6FD2728B680E5868E4560C86C527B21099DCEC81
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 92 ed 0d d5 75 f9 0c 95-ed 08 73 73 af f3 6c c3   ....u.....ss..l.
    0010 - 79 1e 45 ac 56 b0 22 22-5a 3d 37 49 39 52 14 18   y.E.V.""Z=7I9R..
    0020 - 1f 72 26 37 7e 78 22 cc-f7 6c 9e 37 67 8b 19 29   .r&7~x"..l.7g..)
    0030 - 50 82 1e c0 58 9a c0 df-03 e7 20 52 e1 fa 5b f6   P...X..... R..[.
    0040 - 58 61 f3 20 b3 ab 04 92-75 99 62 23 87 c3 e5 45   Xa. ....u.b#...E
    0050 - e7 7e 2e 3d 8b d3 58 c4-7c e3 9c aa 38 ed 24 08   .~.=..X.|...8.$.
    0060 - 9f cc a0 0f 71 8b 0f 26-c3 63 9d f0 51 3b 14 75   ....q..&.c..Q;.u
    0070 - f5 97 39 9a 7c fe 80 e3-23 92 80 12 34 1f 2a 68   ..9.|...#...4.*h
    0080 - b8 fe 9f 8d 11 da ad 26-24 0a 8c f9 e9 91 de 73   .......&$......s
    0090 - 23 c8 e6 86 40 4d b8 b5-33 0b 76 54 60 8d dc de   #...@M..3.vT`...
    00a0 - 97 c6 79 d6 05 66 77 31-ee 55 9a 08 53 1a 3a 97   ..y..fw1.U..S.:.
    00b0 - ec 79 91 d4 1b 4b fe 9c-60 2a 4c 64 10 54 2a 18   .y...K..`*Ld.T*.
    00c0 - 1c e6 72 42 2e 23 f2 aa-2f 48 d2 f9 bb bc 90 75   ..rB.#../H.....u

    Start Time: 1708621498
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
```
## Notas adicionales 
para este ejercicio usamos nmap que es un escaniador de puertos que nos indica cuales son los que estan abiertos y tambien utilizamos ssl para que nos de la clave es igual como en el otro nivel pero nomas buscamos cual puerto esta abierto con el nmap
## Referencias 
https://en.wikipedia.org/wiki/Port_scanner