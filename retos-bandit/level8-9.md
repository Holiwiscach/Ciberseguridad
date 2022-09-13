# Level 8-9
## Objetivo
La clave para el siguiente nivel esta almacenado en el archivo **data.txt** y esta es la unica linea de texto que ocurre una vez.

## Datos de acceso
bandit.labs.overthewire.org
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE0

## Solución
``` bash
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$ 
```

## Notas adicionales

## Referencias
[Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)