## Objetivo
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.
## Datos de acceso al nivel
bandit18@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
## Solucion
```
C:\Users\RIVER\Desktop>ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

C:\Users\RIVER\Desktop>
```
## Notas adicionales 
podemos poner un cat readme tambien cuando queramos entrar a la maquina para que nos de la contraseña
## Referencias 