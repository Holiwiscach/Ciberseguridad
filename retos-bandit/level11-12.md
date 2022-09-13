# Level 11-12
## Objetivo
La clave para el siguiente nivel esta almacenado en el archivo **data.txt**, donde todas las minusculas (a-z) y mayusculas (A-Z) han sido rotadas por 13 posiciones.

## Datos de acceso
bandit.labs.overthewire.org
bandit12
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Solución
``` bash
bandit11@bandit:~$ cat data.txt | tr 'n-za-mN-ZA-M' 'a-zA-Z' 
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$ 
```

## Notas adicionales

## Referencias
[Rot13 on wikipedia](https://en.wikipedia.org/wiki/Rot13)
