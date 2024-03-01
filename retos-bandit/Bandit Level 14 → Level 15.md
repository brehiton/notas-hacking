## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
## Datos de acceso al nivel
ssh -i sshkey.private bandit14@localhost -p 2220 con este comando podemos entrar al siguiente nivel
o
bandit14@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
## Solucion
```
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

^C
bandit14@bandit:~$ echo "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq" | nc |
> localhost 30000
usage: nc [-46CDdFhklNnrStUuvZz] [-I length] [-i interval] [-M ttl]
          [-m minttl] [-O length] [-P proxy_username] [-p source_port]
          [-q seconds] [-s sourceaddr] [-T keyword] [-V rtable] [-W recvlimit]
          [-w timeout] [-X proxy_protocol] [-x proxy_address[:port]]
          [destination] [port]
localhost: command not found
bandit14@bandit:~$ echo "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq" | nc localhost 30000
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

bandit14@bandit:~$ nc -lnvp 4000
Listening on 0.0.0.0 4000
hola quien eres
xxd
^C
bandit14@bandit:~$
```
## Notas adicionales 
conoci el comando "nc" que podemos utilizarlo para conetarnos a puertos por ejemplo nc localhost 30000 y despues la contraseña 
## Referencias 
https://es.wikipedia.org/wiki/Netcat#:~:text=Netcat%20es%20una%20herramienta%20de,remotamente)%20y%20forzar%20conexiones%20UDP%2F