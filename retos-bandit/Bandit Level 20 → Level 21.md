## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think
## Datos de acceso al nivel
bandit20@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
## Solucion
```
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15600 Oct  5 06:19 suconnect
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ nc -lnvp 2020
Listening on 0.0.0.0 2020
yo
^C
bandit20@bandit:~$ nc -lnvp 2020
Listening on 0.0.0.0 2020
Connection received on 127.0.0.1 42236
zy
bandit20@bandit:~$ nc -lnvp 2020
Listening on 0.0.0.0 2020
Connection received on 127.0.0.1 53140
bandit20@bandit:~$ nc -lnvp 2020
Listening on 0.0.0.0 2020
Connection received on 127.0.0.1 56758

FAIL!
bandit20@bandit:~$ nc localhost 2020
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
^C
bandit20@bandit:~$ nc -lnvp 3456 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 143705
bandit20@bandit:~$ Listening on 0.0.0.0 3456

bandit20@bandit:~$
bandit20@bandit:~$ Connection received on 127.0.0.1 39592
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

[1]+  Done                    nc -lnvp 3456 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ ./suconnect 3456
Could not connect
bandit20@bandit:~$ jobs
bandit20@bandit:~$ nc -lnvp 3456 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 147202
bandit20@bandit:~$ Listening on 0.0.0.0 3456

bandit20@bandit:~$ Connection received on 127.0.0.1 58898
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
nc -lnvp 3456 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[2] 147527
[1]   Done                    nc -lnvp 3456 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ Listening on 0.0.0.0 3456

bandit20@bandit:~$ nc -lnvp 34561 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[3] 148250
bandit20@bandit:~$ Listening on 0.0.0.0 34561

bandit20@bandit:~$ ./suconnect 34561
Connection received on 127.0.0.1 59990
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[3]+  Done                    nc -lnvp 34561 <   < VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```
## Notas adicionales 
aqui dice que necesitamos abrir cualquier puerto y agregarle la contraseña para que no la arrogue entonces con el comando **nc -lnvp 1234 <<< y la contraseña de anterior nivel mas el amperson para que no se cierre** y despues tenemos que agregar ./suconnect mas el puerto abierto por nosotros
## Referencias 