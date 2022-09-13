# Level 9-10
## Objetivo
La clave para el siguiente nivel esta almacenado en el archivo **data.txt** en una de las pocas lineas **human-readable**, precedida por varios **'-'** caracteres.

## Datos de acceso
bandit.labs.overthewire.org
bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solución
``` bash
bandit9@bandit:~$ cat data.txt | strings | grep ==
========== the
bu========== password
4iu========== is
b~==P
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$ 

```

## Notas adicionales

## Referencias