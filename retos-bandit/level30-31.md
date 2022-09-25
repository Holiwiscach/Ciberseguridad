# Level 30-31
## Objetivo
Hay un repositorio de git en ssh://bandit30-git@localhost/home/bandit30-git/repo. La contraseña para el usuario bandit30-git es la misma que para el usuario bandit30.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
**bandit30**
**5b90576bedb2cc04c86a9e924ce42faf**

## Solución
``` bash
bandit30@bandit:~$ mkdir /tmp/Arep
bandit30@bandit:~$ cd /tmp/Arep
bandit30@bandit:/tmp/Arep$ git clone ssh://bandit30-git@localhost/home/bandit30-git/repo
Cloning into 'repo'...
Could not create directory '/home/bandit30/.ssh'.
The authenticity of host 'localhost (127.0.0.1)' can't be established.
ECDSA key fingerprint is SHA256:98UL0ZWr85496EtCRkKlo20X3OPnyPSB5tB5RPbhczc.
Are you sure you want to continue connecting (yes/no)? yes
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password: 
remote: Counting objects: 4, done.
remote: Total 4 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/Arep$ cd repo
bandit30@bandit:/tmp/Arep/repo$ cat README.md 
just an epmty file... muahaha
bandit30@bandit:/tmp/Arep/repo$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
bandit30@bandit:/tmp/Arep/repo$ git branch
* master
bandit30@bandit:/tmp/Arep/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/master
bandit30@bandit:/tmp/Arep/repo$ git tag
secret
bandit30@bandit:/tmp/Arep/repo$ git show secret
47e603bb428404d265f59c42920d81e5

```

## Notas adicionales
- **show secret** nos ayuda a mostrar el contenido dentro de el archivo secreto

## Referencias