# Level 20-21
## Objetivo
Hay un binario setuid en el directorio de inicio que hace lo siguiente: establece una conexión con localhost en el puerto que especifique como argumento de la línea de comandos. Luego lee una línea de texto de la conexión y la compara con la contraseña del nivel anterior (bandit20). Si la contraseña es correcta, transmitirá la contraseña para el siguiente nivel (bandit21).

NOTA: intente conectarse a su propio demonio de red para ver si funciona como cree.

## Datos de acceso}
bandit.labs.overthewire.org
bandit21
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

## Solución
nc -l bp 3030

``` bash
bandit20@bandit:~$ ls -al
total 32
drwxr-xr-x  2 root     root      4096 May  7  2020 .
drwxr-xr-x 41 root     root      4096 May  7  2020 ..
-rw-r--r--  1 root     root       220 May 15  2017 .bash_logout
-rw-r--r--  1 root     root      3526 May 15  2017 .bashrc
-rw-r--r--  1 root     root       675 May 15  2017 .profile
-rwsr-x---  1 bandit21 bandit20 12088 May  7  2020 suconnect
bandit20@bandit:~$ ls -al ./suconnect 
-rwsr-x--- 1 bandit21 bandit20 12088 May  7  2020 ./suconnect
bandit20@bandit:~$ echo "NvEJF7oVjkddltPSrdKEFOllh9V1IBcq" | nc -l localhost -p 61337 &
[1] 7583
bandit20@bandit:~$ ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
bandit20  1856  0.0  0.0  19328  2948 pts/16   S+   18:51   0:00 tmux -2
bandit20  1858  0.0  0.0  28204  3624 ?        Ss   18:51   0:01 tmux -2
bandit20  1859  0.0  0.1  21192  5036 pts/41   Ss+  18:51   0:00 -bash
bandit20  1889  0.0  0.1  21192  5036 pts/12   Ss+  19:17   0:00 -bash
bandit20  3545  0.0  0.1  21192  4928 pts/79   Ss+  19:19   0:00 -bash
bandit20  3651  0.0  0.1  21192  4976 pts/88   Ss+  19:19   0:00 -bash
bandit20  4646  0.0  0.0   4180   680 pts/73   T    19:20   0:00 nc -l 1000
bandit20  6512  0.0  0.0   4180   640 pts/73   T    19:23   0:00 nc -l 1000
bandit20  7583  0.0  0.0   6300  1616 pts/71   S    19:24   0:00 nc -l localhost -p 61337
bandit20  8032  0.0  0.0  19188  2476 pts/71   R+   19:25   0:00 ps aux
bandit20 14588  0.0  0.0  23464  2228 pts/41   T    19:01   0:00 ncat -l 43210
bandit20 18340  0.0  0.1  21192  5012 pts/46   Ss   19:03   0:00 -bash
bandit20 21982  0.0  0.0  19328  2984 pts/46   S+   19:05   0:00 tmux
bandit20 23717  0.0  0.1  21192  4968 pts/18   Ss   19:07   0:00 -bash
bandit20 24953  0.0  0.0  27980  2520 ?        Ss   18:39   0:00 SCREEN
bandit20 24954  0.0  0.1  21188  5076 pts/16   Ss   18:39   0:00 /bin/bash
bandit20 25173  0.0  0.1  21240  5284 pts/73   Ss+  19:09   0:00 -bash
bandit20 25968  0.0  0.1  21148  4992 pts/68   Ss+  19:10   0:00 -bash
bandit20 26209  0.0  0.0  17000  2960 pts/18   S+   19:10   0:00 man ls
bandit20 26221  0.0  0.0   8196   888 pts/18   S+   19:10   0:00 pager
bandit20 26993  0.0  0.1  21148  4864 pts/36   Ss+  19:11   0:00 -bash
bandit20 27783  0.0  0.1  21320  5336 pts/71   Ss   19:12   0:00 -bash
bandit20 27824  0.0  0.1  21168  5200 pts/81   Ss+  19:12   0:00 -bash
bandit20 29033  0.0  0.0   4180   692 pts/73   T    19:14   0:00 nc -l 1000
bandit20 29247  0.0  0.0   4180   672 pts/73   T    19:14   0:00 nc -l 1000
bandit20@bandit:~$ ./suconnect 61337
Read: GbKksEFF4yrVs6il55v6gwY5aVje5f0j
Password matches, sending next password
gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
[1]+  Done                    echo "NvEJF7oVjkddltPSrdKEFOllh9V1IBcq" | nc -l localhost -p 61337





```


## Notas adicionales


## Referencias