kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

# Level 17-18
## Objetivo
Estos 2 archivos en el home directory: passwaords.old and passwords.new. La clave para el siguiente nivel es un passwords.new y esta unica linea que ha cambiado entre passwords.old y passwords.new

## Datos de acceso
bandit.labs.overthewire.org
bandit18
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Solución
**dif passwaords.old passwords.new**

``` bash
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< 09wUIyMU4YhOzl1Lzxoz0voIBzZ2TUAf
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$ 

```


## Notas adicionales
Comando head muestra las ultimas lineas

- head -n 10
- tail -n15
- wc

**diff** muestra las diferencias entre dos archivos

## Referencias