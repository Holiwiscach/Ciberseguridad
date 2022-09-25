# Level 32-33
## Objetivo
Después de todo esto, es hora de otro escape. ¡Buena suerte!

## Datos de acceso
**bandit32**
**56a9bf19c63d650ce78e6ec0354ee45e**

## Solución
```bash

WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: not found
>> sh 
sh: 1: SH: not found
>> more 
sh: 1: MORE: not found
>> clear
sh: 1: CLEAR: not found
>> pwd
sh: 1: PWD: not found
>> $0
$ pwd
/home/bandit32
$ ls -la
total 28
drwxr-xr-x  2 root     root     4096 May  7  2020 .
drwxr-xr-x 41 root     root     4096 May  7  2020 ..
-rw-r--r--  1 root     root      220 May 15  2017 .bash_logout
-rw-r--r--  1 root     root     3526 May 15  2017 .bashrc
-rw-r--r--  1 root     root      675 May 15  2017 .profile
-rwsr-x---  1 bandit33 bandit32 7556 May  7  2020 uppershell
$ cat upershell	
cat: upershell: No such file or directory
$ cd /tmp/bandit_pass/bandit32
sh: 4: cd: can't cd to /tmp/bandit_pass/bandit32
$  cd /tmp/bandit_pass/bandit32
sh: 5: cd: can't cd to /tmp/bandit_pass/bandit32
$ cd /etc/bandit_pass/bandit32
sh: 6: cd: can't cd to /etc/bandit_pass/bandit32
$ cd /etc/bandit_pass/bandit33
sh: 7: cd: can't cd to /etc/bandit_pass/bandit33
$ cat /etc/bandit_pass/bandit33
c9c3199ddf4121b10cf581a98d51caee

## Notas adicionales

## Referencias