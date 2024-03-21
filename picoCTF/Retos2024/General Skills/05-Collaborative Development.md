## Objetivo
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/176/challenge.zip)
## Pistas
`git branch -a` will let you see available branches

How can file 'diffs' be brought to the main branch? Don't forget to `git config`!

Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.
## Solucion
```
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/05-Collaborative Development/drop-in]
└─$ git branch -a                                                
* feature/part-1
  feature/part-2
  feature/part-3
  main
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/05-Collaborative Development/drop-in]
└─$ git checkout feature/part-1                                  
Already on 'feature/part-1'
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/05-Collaborative Development/drop-in]
└─$ python3 flag.py       
Printing the flag...
picoCTF{t3@mw0rk_                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/05-Collaborative Development/drop-in]
└─$ git checkout feature/part-2
Switched to branch 'feature/part-2'
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/05-Collaborative Development/drop-in]
└─$ python3 flag.py
Printing the flag...
m@k3s_th3_dr3@m_                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/05-Collaborative Development/drop-in]
└─$ git checkout feature/part-3
Switched to branch 'feature/part-3'
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/05-Collaborative Development/drop-in]
└─$ python3 flag.py
Printing the flag...
w0rk_2c91ca76}
                                                                                                                                                                       
┌──(hectorr㉿kali2024)-[~/…/Retos2024/General Skills/05-Collaborative Development/drop-in]
└─$ 

picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}
```
## Notas adicionales 
hicimos el uso de **git branch -a** para ver todos los directorios y para agregarlos a la pantalla principal hicimos el uso de **git chechout mas los que habia adentro de git branch -a** y fui ejecutando el python3 que estaba ahi 
## Referencias 