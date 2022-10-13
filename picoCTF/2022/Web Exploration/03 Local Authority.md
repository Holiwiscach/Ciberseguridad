# Local Authority
Can you get the flag? Go to this [website](http://saturn.picoctf.net:52682/) and see what you can discover.

Hints:
- How is the password checked on this website?

## Solución
Entrando a la página lo que se tiene que hacer es inspeccionar el codigo fuente de la web. Una vez dentro entramos a un archivo llamado **login.php**

``` html
<body>

    <h1>Secure Customer Portal</h1>
    
   <p>Only letters and numbers allowed for username and password.</p>
    
    <form role="form" action="[login.php](view-source:http://saturn.picoctf.net:52682/login.php)" method="post">
      <input type="text" name="username" placeholder="Username" required 
       autofocus></br>
      <input type="password" name="password" placeholder="Password" required>
      <button type="submit" name="login">Login</button>
    </form>
  </body>
```

Dentro enocntraremos un script **secure.js** donde encontraremos el username y el password para poder logearnos.

``` html
<body>
    <script src="[secure.js](view-source:http://saturn.picoctf.net:52682/secure.js)"></script>
    
    <p id='msg'></p>
    
    <form hidden action="[admin.php](view-source:http://saturn.picoctf.net:52682/admin.php)" method="post" id="hiddenAdminForm">
      <input type="text" name="hash" required id="adminFormHash">
    </form>
    ..........
```

``` js
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

obteniendo la bandera

picoCTF{j5_15_7r4n5p4r3n7_a8788e61}