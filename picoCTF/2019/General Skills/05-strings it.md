# strings it
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

Hints:
- [strings](https://linux.die.net/man/1/strings)

## Solución
Usamos el comando strings en el archivo que tambien tiene ese mismo nombre, y usamos un grep buscando la palabra picoCTF
``` bash
holiwiscach@ubuntu:~$ strings strings | grep 'picoCTF'
picoCTF{5tRIng5_1T_7f766a23}
```