# Level 25-26
## Objetivo
Iniciar sesión en bandit26 desde bandit25 debería ser bastante fácil... El shell para el usuario bandit26 no es /bin/bash, sino otra cosa. Descubra qué es, cómo funciona y cómo salir de él.

## Datos de acceso
bandit.labs.overthewire.org
bandit26
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

## Solución

``` bash
bandit25@bandit:~$ cat /etc/passwd | grep bandit26  
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/**showtext**bandit25@bandit:~$ cat /usr/bin/showtext  
#!/bin/shexport TERM=linux**more ~/text.txt**  

c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
exit 0
```

## Notas adicionales

## Referencias