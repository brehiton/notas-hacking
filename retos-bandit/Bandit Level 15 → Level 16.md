## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**
## Datos de acceso al nivel
bandit15@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
## Solucion
bandit14@bandit:~$ openssl s_client -connect localhost:30001
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
MIIDCzCCAfOgAwIBAgIEIivS1jANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTc1MDA2WhcNMjQwMjIwMTc1MTA2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC4
XC9dgne8ha9I/vXn4uTtObLhI/PPyLyl4jyDQPp61VtsEMcOb95KhXxdtQiDtzSD
3KXQVFLaPlVGKDWSR9nV+GoazSNPmNLH/IMVrUYxXjYikPxo1jjYKyuqfjV5bNm3
Hz6z4eDl7wNbPRaPAMPo0WU23m9M04bKQHLINfN7Abz3a+7ChLeICrWXiXp9mWfj
PY8cK7Vayz0eHU4Lg64q4jUaXQqZ/ta1RqZEwv7ZuTKctcazpK/u2+h4zvQCPyLh
uDjUXZTLlIuhfjyKUJLQsmYHAQprV6sY3ybFN32dW6MSE0/ApT6Th0LzKeaYxk5b
3NIeaYyPeKsjqFSwy+2zAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBQ
RXG1k+cB357X43fsiyaCQQh4RbWHOcg1jBes5eiC/H8MyC3ec1znXvOUfqJcWNQJ
9UJDMwbkpo+IcwJiOe9n/D3Zeypv1g+ta8KKLsQ+zcbp5RdltKy7GuO/s5WjVofE
/IHz/5g+IMoqqYLlquQ539CZykPMC9TB9uWfJj/i8faCox4gjtkSCri+27tUZuHi
eYR3zxY1ptsJti/pMaItC6Oc2/pSlotQ4fXdciLZYGXqlmSFBt8Y8/v1YkhME5gN
3HmBV/Zg1SghA57zYsbf3npvQwudr04f2iF493pe0VRN6DfiXTxWkJe1VKuyGHEr
Q4L4OdVlgMSeyYyKgFc7
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
    Session-ID: 1A2680D2FB4DD1F701C9CE1D737991E1E17B43E23CE898C5DFA9B026B36CAD7A
    Session-ID-ctx:
    Resumption PSK: 75D547C973392C52CB85F53A697FA778723B7E4875C61BE01BF055F558FB2FB31A3D0F0D443D374AD7083BE03906E34D
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - f6 58 07 2f ae 72 e8 63-bc 7a 9e 69 be c3 39 75   .X./.r.c.z.i..9u
    0020 - 6a 12 93 fa 11 78 eb db-b7 46 20 6b e8 74 9b 73   j....x...F k.t.s
    0030 - 31 d0 56 6e 5b 78 55 e3-10 65 ce 47 ef 40 a6 55   1.Vn[xU..e.G.@.U
    0040 - d5 8c 96 2f f0 42 4c cf-13 3f 52 db 75 ab 37 33   .../.BL..?R.u.73
    0050 - 54 a7 95 6a 1c 22 93 19-91 40 46 14 69 8a 73 9f   T..j."...@F.i.s.
    0060 - 99 b0 80 71 b3 48 72 92-95 d6 62 e2 ab 73 35 28   ...q.Hr...b..s5(
    0070 - f0 a3 71 71 19 67 a5 12-03 81 d5 7e 63 08 32 f5   ..qq.g.....~c.2.
    0080 - b6 49 43 37 eb 7c a2 3c-93 28 81 d6 4c c0 b1 f3   .IC7.|.<.(..L...
    0090 - db ab eb a7 4b d8 86 9d-9d 30 3c 46 6c 10 e2 74   ....K....0<Fl..t
    00a0 - 99 1a 13 10 33 34 d8 96-aa 94 95 8f da 28 a9 11   ....34.......(..
    00b0 - a6 68 31 79 4b 8e 6c 02-6d e9 24 2b 72 e7 96 ec   .h1yK.l.m.$+r...
    00c0 - 69 de f0 5f 61 33 8a 79-ec 73 bf cf 5e e2 0a d1   i.._a3.y.s..^...

    Start Time: 1708477306
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
    Session-ID: 644AF34817655767AF4991AC3BA804B45C57EA32C77DF979F5DBF6EF74C72C14
    Session-ID-ctx:
    Resumption PSK: 78E6C4DDE20C135254992C67265638598647DDD21DAB39434C11DADCB61A25EC15421FC1BBB3CB6205BEB45A62DA631E
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - b4 b7 38 b2 0d 32 fb 51-c2 7d fc 2f 83 44 e7 dd   ..8..2.Q.}./.D..
    0020 - fe 6f 2c c1 93 73 28 0b-9c dd 20 5d 2d 3b 9b 4c   .o,..s(... ]-;.L
    0030 - 9e 4b 67 ca f9 0c a6 23-d3 10 c3 a4 f5 63 e0 5e   .Kg....#.....c.^
    0040 - 00 8d 96 de c3 29 d6 f1-d6 dd fd 33 85 3c 8a b1   .....).....3.<..
    0050 - 60 8b 9d 0b 0f 0a 51 25-2c 0f b4 b4 5e 5b 9d 27   `.....Q%,...^[.'
    0060 - f4 c2 04 ed 6f 26 a4 76-a6 55 51 c4 c5 c2 94 aa   ....o&.v.UQ.....
    0070 - 6d 2a 2d 7a f7 97 45 2f-f7 13 aa d7 d8 e2 f0 38   m*-z..E/.......8
    0080 - b7 64 67 79 e0 a0 3c 9e-ec 0e 62 34 0b 6f c7 c7   .dgy..<...b4.o..
    0090 - a3 11 d7 3d af 67 7c 4d-43 a5 9e 1d 12 97 9c 4c   ...=.g|MC......L
    00a0 - 11 62 c5 23 56 c9 67 37-94 d2 a2 41 2f 0f 9c 86   .b.#V.g7...A/...
    00b0 - 4a 5d 55 f7 85 d0 18 8a-4c 7b 10 61 4a 62 30 3b   J]U.....L{.aJb0;
    00c0 - 5a 8a 26 42 06 21 bd 45-52 c4 09 17 4e de 34 71   Z.&B.!.ER...N.4q

    Start Time: 1708477306
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit14@bandit:~$
## Notas adicionales 
aprendimos sobre como conectarnos en ssl o tambien conocido como tls 
y cuando nos conectamos al ssl pusimos la contrraseña del anterior nivel y podimos resolver el ejercicio.
nota importante:  "openssl s_client -connect " con este comando nos podemos conectar mas el localhost y el puerto abierto.
## Referencias 
https://en.wikipedia.org/wiki/Secure_Socket_Layer
https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html