## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm) has extraordinarily helpful information...
## Pistas
This program will only work in the webshell or another Linux computer.

To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm`

Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`

-h and --help are the most common arguments to give to programs to get more information from them!

Not every program implements help features like -h and --help.
## Solucion
'''
brehiton2-picoctf@webshell:~$ ls
README.txt  ciphertext  ciphertext.1  ciphertext.2  flag  new_caesar.py  warm
brehiton2-picoctf@webshell:~$  wget https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
--2024-02-27 18:46:46--  https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm.1'

warm.1                                          100%[======================================================================================================>]  10.68K  --.-KB/s    in 0s      

2024-02-27 18:46:46 (101 MB/s) - 'warm.1' saved [10936/10936]

brehiton2-picoctf@webshell:~$ chmod +x warm
brehiton2-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
brehiton2-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_30e77291}
'''
## Notas adicionales 
aprendi a dar permisos con +x a archivos y el menos **-h** me dio la bandera 
## Referencias 