# Level 27-28
## Objetivo
Hay un repositorio de git en ssh://bandit27-git@localhost/home/bandit27-git/repo. La contraseña para el usuario bandit27-git es la misma que para el usuario bandit27.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
**bandit27**
**3ba3118a22e93127a4ed485be72ef5ea**

## Solución
``` bash
bandit27@bandit:~$ mkdir /tmp/repo
bandit27@bandit:~$ cd /tmp/repo
bandit27@bandit:/tmp/repo$ ls -la
total 1992
drwxr-sr-x 2 bandit27 root    4096 Feb 20 04:41 .
drwxrws-wt 1 root     root 2031616 Feb 20 04:41 ..
bandit27@bandit:/tmp/repo$ git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
Cloning into 'repo'...
Could not create directory '/home/bandit27/.ssh'.
The authenticity of host 'localhost (127.0.0.1)' can't be established.
ECDSA key fingerprint is SHA256:98UL0ZWr85496EtCRkKlo20X3OPnyPSB5tB5RPbhczc.
Are you sure you want to continue connecting (yes/no)? yes
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password: 
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/repo$ ls -la
total 1996
drwxr-sr-x 3 bandit27 root    4096 Feb 20 04:41 .
drwxrws-wt 1 root     root 2031616 Feb 20 04:42 ..
drwxr-sr-x 3 bandit27 root    4096 Feb 20 04:42 repo
bandit27@bandit:/tmp/repo$ ls repo
README
bandit27@bandit:/tmp/repo$ cat repo/README
The password to the next level is: 0ef186ac70e04ea33b4c1853d2526fa2
```

## Notas adicionales

## Referencias