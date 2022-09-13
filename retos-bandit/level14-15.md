# Level 14-15
## Objetivo
La clave para el siguiente nivel puede ser recuperar enviado la contrasela del nivel al actual puerto a 30000 en localhost.

## Datos de acceso
bandit.labs.overthewire.org
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución
``` bash
bandit14@bandit:~$ nc localhost 30000 -v
Connection to localhost (127.0.0.1) 30000 port [tcp/*] succeeded!
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt


bandit14@bandit:~$ 

```

## Notas adicionales
**nc** sirve para conectarse a servidores remotos

## Referencias
[How the internet works in 5 minutes](https://www.youtube.com/watch?v=7_LPdttKXPc)(Not completely accurate, but goof enough for beginners)
[IP Address](http://computer.howstuffworks.com/web-server5.htm)
[IP Address on wikipedia](https://en.wikipedia.org/wiki/IP_address)
[Localhost on wikipedia](https://en.wikipedia.org/wiki/Localhost)
[Ports](http://computer.howstuffworks.com/web-server8.htm)
[Ports (computer networking) on wikipedia](https://en.wikipedia.org/wiki/Port_(computer_networking))
