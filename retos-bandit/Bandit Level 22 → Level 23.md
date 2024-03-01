## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
## Datos de acceso al nivel
bandit22@bandit.labs.overthewire.org -p 2220
contraseña del anterior nivel: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
## Solucion
```
bandit22@bandit:~$ ls /etc/cron.d -la
total 56
drwxr-xr-x   2 root root  4096 Oct  5 06:20 .
drwxr-xr-x 106 root root 12288 Oct  5 06:20 ..
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit15_root
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit17_root
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit22
-rw-r--r--   1 root root   122 Oct  5 06:19 cronjob_bandit23
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit24
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit25_root
-rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
-rwx------   1 root root    52 Oct  5 06:20 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root   396 Feb  2  2021 sysstat
bandit22@bandit:~$ ls /etc/cron.d/cronjob_bandit23
/etc/cron.d/cronjob_bandit23
bandit22@bandit:~$ cat  /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ whoami
bandit22
bandit22@bandit:~$ mymane=$(whoami)
bandit22@bandit:~$ echo mymane
mymane
bandit22@bandit:~$ myname=$(whoami)
bandit22@bandit:~$ echo myname
myname
bandit22@bandit:~$ myname=$(whoami)
bandit22@bandit:~$ myname
myname: command not found
bandit22@bandit:~$ echo myname
myname
bandit22@bandit:~$ echo $myname
bandit22
bandit22@bandit:~$ echo I am user $myname
I am user bandit22
bandit22@bandit:~$ echo I am user $myname | md5sum
8169b67bd894ddbb4412f91573b38db3  -
bandit22@bandit:~$ echo I am user $myname | md5sum | cut -d ' ' -f 1
8169b67bd894ddbb4412f91573b38db3
bandit22@bandit:~$ myname=bandit23
bandit22@bandit:~$ echo I am user $myname | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
bandit22@bandit:~$
```
## Notas adicionales 
entramos al directorio de **/etc/cron.d/** con un ls para solamente ver, le hacemos un cat al archivo 23 que es el que esperamos resolver, es un tipo bash lo sabremos por que tiene **#!/bin/bash** ejecutamos los que nos muestra si es que lleva un echo, y para ver el mensaje seria primero el $y el comando y ya despues nos dara la contraseña.
siempre con un cat y echo para el bash
## Referencias 