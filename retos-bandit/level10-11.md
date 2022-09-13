# Level 10-11
## Objetivo
La clave para el siguiente nivel esta almacenado en el archivo **data.txt** que contiene **base64** datos codificados.

## Datos de acceso
bandit.labs.overthewire.org
bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución
``` bash
bandit10@bandit:~$ base64 --decode data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$ 
```

## Notas adicionales

## Referencias
[Base64 on wikipedia](https://en.wikipedia.org/wiki/Base64)