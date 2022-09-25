# Level 19-20
## Objetivo
Para ganar el acceso al siguiente nivel, deberas usar el setuid binary en el homedirectory. Ejecutalo sin argumentos para que descubras como usarlo. La clave para este nivel puede ser encontrado en el mismo lugar (/etc/bandit_pass), despues tienes que usar el setuid binary.

## Datos de acceso
bandit.labs.overthewire.org
bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solución

``` bash
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$ 

```


## Notas adicionales
- el **-rwsr-x---** nos dice que tenemos permiso de usarlo en mobre del usuario al que le pertenece

## Referencias
[setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)