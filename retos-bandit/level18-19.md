# Level 18-19
## Objetivo
La clave para el siguiente nivel esta almacenado en un archivo en el homedirectory. Desafortunadamente, alguien ha modificado .bashrc para sacarte cuando entras con SSH.

## Datos de acceso
bandit.labs.overthewire.org
bandit19
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

## Solución
ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash

``` bash
holiwiscach@ubuntu:~$ ssh bandit18@bandit.labs.overthewire.org -p 2220 ls
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
Permission denied, please try again.
bandit18@bandit.labs.overthewire.org's password: 
readme

holiwiscach@ubuntu:~$ ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
holiwiscach@ubuntu:~$ 

```

## Notas adicionales
**ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash** crear una linea de comandos antes de que salga del log 

## Referencias