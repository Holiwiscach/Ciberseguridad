# Level 28-29
## Objetivo
Hay un repositorio de git en ssh://bandit28-git@localhost/home/bandit28-git/repo. La contraseña para el usuario bandit28-git es la misma que para el usuario bandit28.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
**bandit28**
**0ef186ac70e04ea33b4c1853d2526fa2**

## Solución
``` bash
bandit28@bandit:/tmp/repo$ sudo rm -rf repo
sudo: /usr/bin/sudo must be owned by uid 0 and have the setuid bit set
bandit28@bandit:/tmp/repo$ cd ..
bandit28@bandit:/tmp$ mkdir repositorio
bandit28@bandit:/tmp$ cd repositorio
bandit28@bandit:/tmp/repositorio$ git clone ssh://bandit28-git@localhost/home/bandit28-git/repo
Cloning into 'repo'...
Could not create directory '/home/bandit28/.ssh'.
The authenticity of host 'localhost (127.0.0.1)' can't be established.
ECDSA key fingerprint is SHA256:98UL0ZWr85496EtCRkKlo20X3OPnyPSB5tB5RPbhczc.
Are you sure you want to continue connecting (yes/no)? yes
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

bandit28-git@localhost's password: 
remote: Counting objects: 9, done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0)
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/repositorio$ ls -la
total 1996
drwxr-sr-x 3 bandit28 root    4096 Feb 20 04:59 .
drwxrws-wt 1 root     root 2031616 Feb 20 05:00 ..
drwxr-sr-x 3 bandit28 root    4096 Feb 20 05:00 repo
bandit28@bandit:/tmp/repositorio$ cat repo/README
cat: repo/README: No such file or directory
bandit28@bandit:/tmp/repositorio$ cd repo
bandit28@bandit:/tmp/repositorio/repo$ ls -la
total 16
drwxr-sr-x 3 bandit28 root 4096 Feb 20 05:00 .
drwxr-sr-x 3 bandit28 root 4096 Feb 20 04:59 ..
drwxr-sr-x 8 bandit28 root 4096 Feb 20 05:00 .git
-rw-r--r-- 1 bandit28 root  111 Feb 20 05:00 README.md
bandit28@bandit:/tmp/repositorio/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/repositorio/repo$ cat README.md decode
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

cat: decode: No such file or directory
bandit28@bandit:/tmp/repositorio/repo$ 
bandit28@bandit:/tmp/repositorio/repo$ cat README.md -decode
cat: invalid option -- 'd'
Try 'cat --help' for more information.
bandit28@bandit:/tmp/repositorio/repo$ cat README.md |decode
-bash: decode: command not found
bandit28@bandit:/tmp/repositorio/repo$ git log
commit edd935d60906b33f0619605abd1689808ccdd5ee
Author: Morla Porla <morla@overthewire.org>
Date:   Thu May 7 20:14:49 2020 +0200

    fix info leak

commit c086d11a00c0648d095d04c089786efef5e01264
Author: Morla Porla <morla@overthewire.org>
Date:   Thu May 7 20:14:49 2020 +0200

    add missing data

commit de2ebe2d5fd1598cd547f4d56247e053be3fdc38
Author: Ben Dover <noone@overthewire.org>
Date:   Thu May 7 20:14:49 2020 +0200

    initial commit of README.md
bandit28@bandit:/tmp/repositorio/repo$ git log -p -1
commit edd935d60906b33f0619605abd1689808ccdd5ee
Author: Morla Porla <morla@overthewire.org>
Date:   Thu May 7 20:14:49 2020 +0200

    fix info leak

diff --git a/README.md b/README.md
index 3f7cee8..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials
 
 - username: bandit29
	-- password: bbc96594b4e001778eee9975372716b2
+- password: xxxxxxxxxx
 
bandit28@bandit:/tmp/repositorio/repo$ diff --git a/README.md b/README.md 
diff: unrecognized option '--git'
diff: Try 'diff --help' for more information.
bandit28@bandit:/tmp/repositorio/repo$ diff --git a/README.md b/README.md 
```

## Notas adicionales

## Referencias