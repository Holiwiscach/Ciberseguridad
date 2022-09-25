# Level 31-32
## Objetivo
Hay un repositorio de git en ssh://bandit31-git@localhost/home/bandit31-git/repo. La contraseña para el usuario bandit31-git es la misma que para el usuario bandit31.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
**bandit31**
**47e603bb428404d265f59c42920d81e5**

## Solución
``` bash
bandit31@bandit:/tmp/Atemp/repo$ git pull origin main
Could not create directory '/home/bandit31/.ssh'.
The authenticity of host 'localhost (127.0.0.1)' can't be established.
ECDSA key fingerprint is SHA256:98UL0ZWr85496EtCRkKlo20X3OPnyPSB5tB5RPbhczc.
Are you sure you want to continue connecting (yes/no)? yes
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password: 
fatal: Couldn't find remote ref main
bandit31@bandit:/tmp/Atemp/repo$ fatal: The remote end hung up unexpectedly
ls
README.md
bandit31@bandit:/tmp/Atemp/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/Atemp/repo$ git branch
* master
bandit31@bandit:/tmp/Atemp/repo$ git pull origin main
Could not create directory '/home/bandit31/.ssh'.
The authenticity of host 'localhost (127.0.0.1)' can't be established.
ECDSA key fingerprint is SHA256:98UL0ZWr85496EtCRkKlo20X3OPnyPSB5tB5RPbhczc.
Are you sure you want to continue connecting (yes/no)? yes
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password: 
fatal: Couldn't find remote ref main
fatal: The remote end hung up unexpectedly
bandit31@bandit:/tmp/Atemp/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/master
bandit31@bandit:/tmp/Atemp/repo$ git branch
bandit31@bandit:/tmp/secttp/repo$ touch key.txt  
bandit31@bandit:/tmp/secttp/repo$ echo "May I come in?" > key.txtbandit31@bandit:/tmp/secttp/repo$ git add key.txt  
The following paths are ignored by one of your .gitignore files:  
key.txt  
Use -f if you really want to add them.  
bandit31@bandit:/tmp/secttp/repo$ ls -al  
total 24  
drwxr-sr-x 3 bandit31 root 4096 Mar 28 11:43 .  
drwxr-sr-x 3 bandit31 root 4096 Mar 28 11:40 ..  
drwxr-sr-x 8 bandit31 root 4096 Mar 28 11:45 .git  
-rw-r--r-- 1 bandit31 root    6 Mar 28 11:40 .gitignore  
-rw-r--r-- 1 bandit31 root   15 Mar 28 11:44 key.txt  
-rw-r--r-- 1 bandit31 root  147 Mar 28 11:40 README.md  
bandit31@bandit:/tmp/secttp/repo$ cat .gitignore  
*.txt
bandit31@bandit:/tmp/secttp/repo$ rm .gitignore  
bandit31@bandit:/tmp/secttp/repo$ git add key.txt  
bandit31@bandit:/tmp/secttp/repo$ git commit -m "actualizamos un archivo"  
[master 45b1ec4] Upload a file  
 1 file changed, 1 insertion(+)  
 create mode 100644 key.txtbandit31@bandit:/tmp/secttp/repo$ git push origin master  
Could not create directory '/home/bandit31/.ssh'.  
The authenticity of host 'localhost (127.0.0.1)' can't be established.  
ECDSA key fingerprint is SHA256:98UL0ZWr85496EtCRkKlo20X3OPnyPSB5tB5RPbhczc.  
Are you sure you want to continue connecting (yes/no)? yes  
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).  
This is a OverTheWire game server. More information on [http://www.overthewire.org/wargames](http://www.overthewire.org/wargames)bandit31-git@localhost's password:  
47e603bb428404d265f59c42920d81e5Counting objects: 3, done.  
Delta compression using up to 4 threads.  
Compressing objects: 100% (2/2), done.  
Writing objects: 100% (3/3), 324 bytes | 0 bytes/s, done.  
Total 3 (delta 0), reused 0 (delta 0)  
remote: ### Attempting to validate files... ####  
remote:  
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.  
remote:  
remote: Well done! Here is the password for the next level:  
remote: **56a9bf19c63d650ce78e6ec0354ee45e**  
remote:  
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.  
remote:  
To ssh://localhost/home/bandit31-git/repo  
 ! [remote rejected] master -> master (pre-receive hook declined)  
error: failed to push some refs to 'ssh://bandit31-git@localhost/home/bandit31-git/repo'  
bandit31@bandit:/tmp/secttp/repo$
```

## Notas adicionales
- **git pull origin master** nos ayuda a traer todo lo que este en la rama master

## Referencias