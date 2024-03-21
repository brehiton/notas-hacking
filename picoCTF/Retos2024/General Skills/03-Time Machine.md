## Objetivo
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/160/challenge.zip)
## Pistas
The `cat` command will let you read a file, but that won't help you here!

Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).

When committing a file with git, a message can (and should) be included.
## Solucion
```
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills/03-Time Machine]
└─$ ls
challenge.zip  drop-in
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills/03-Time Machine]
└─$ cd drop-in         
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/03-Time Machine/drop-in]
└─$ ls
message.txt
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/03-Time Machine/drop-in]
└─$ cat message.txt 
This is what I was working on, but I'd need to look at my commit history to know why...                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/03-Time Machine/drop-in]
└─$ git init                                             
Reinitialized existing Git repository in /home/hectorr/picoCTF/Retos2024/General Skills/03-Time Machine/drop-in/.git/
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/03-Time Machine/drop-in]
└─$ ls
message.txt
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/03-Time Machine/drop-in]
└─$ git log 
commit 89d296ef533525a1378529be66b22d6a2c01e530 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:22 2024 +0000

    picoCTF{t1m3m@ch1n3_186cd7d7}
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/03-Time Machine/drop-in]
└─$ 

```
## Notas adicionales 
lo que hicimos fue hacer un cat al archivo y despues hacer git init, para inicializar despues hicimos el uso del comando **git log** para ver los usuarios y ahi estaba la bANDERA EN LOS USUARIOS
## Referencias