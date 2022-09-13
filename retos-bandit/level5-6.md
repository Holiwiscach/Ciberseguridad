# Level 5-6
## Objetivo
La clave para el siguiente nivel esta almacenada en un algun archivo del directorio **inhere** y tiene las siguientes propiedades
- Human-readable
- 1033 bytes in size
- not executable

## Datos de acceso
bandit.labs.overthewire.org
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Solución
```bash
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
maybehere03  maybehere07  maybehere11  maybehere15  maybehere19
bandit5@bandit:~/inhere$ find -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cd maybehere07
bandit5@bandit:~/inhere/maybehere07$ cat .file2
bandit5@bandit:~/inhere/maybehere07$ 

```

## Notas adicionales
Usando ls -la podemos ver esos archivos que son read-write

## Referencias