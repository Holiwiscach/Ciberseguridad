# Level 13-14
## Objetivo
La clave para el siguiente nivel esta almacenado en **/etc/bandit_pass/bandit14** pero unicamente puede leerlo el usuario bandit14. Para ese nivel, no tienes la clave. Pero con la llave privada SSh puedes estar logeado dentro del siguiente nivel.

NOTA: **localhost** es un hostname que se refiere a la maquina con la cual estas trabajando.

## Datos de acceso
bandit.labs.overthewire.org
bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solución
``` bash
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost
...
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```

## Notas adicionales

## Referencias
[SSH/IpenSSH/Keys](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)