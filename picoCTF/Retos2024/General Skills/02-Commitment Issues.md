## Objetivo
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/136/challenge.zip)
## Pistas
Version control can help you recover files if you change or lose them!

Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)

You can 'checkout' commits to see the files inside them
## Solucion
```
─(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills/drop-in]
└─$ cat message.txt
TOP SECRET
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills/drop-in]
└─$ git init         
Reinitialized existing Git repository in /home/hectorr/picoCTF/Retos2024/General Skills/drop-in/.git/
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills/drop-in]
└─$ git log 
commit 8dc51806c760dfdbb34b33a2008926d3d8e8ad49 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:17 2024 +0000

    remove sensitive info

commit 87b85d7dfb839b077678611280fa023d76e017b8
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:17 2024 +0000

    create flag
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills/drop-in]
└─$ git checkout 87b85d7dfb839b077678611280fa023d76e017b8
Note: switching to '87b85d7dfb839b077678611280fa023d76e017b8'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 87b85d7 create flag
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills/drop-in]
└─$ ls
message.txt
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills/drop-in]
└─$ cat message.txt
picoCTF{s@n1t1z3_ea83ff2a}
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills/drop-in]
└─$ 
```

## Notas adicionales 
primero hicimos un cat despues hicimos la inicializacion con git init para poder inicar entonces utilizamos el comando de git log para ver todos los usuarios y los push que se han echo entoces vimos primero el de mas abajo y le copiamos el codigo y lo pusimos como **git checkout 87b85d7dfb839b077678611280fa023d76e017b8** y despues le hicimos un cat al archivo y no dio la banderita 
## Referencias 