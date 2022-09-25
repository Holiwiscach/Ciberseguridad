# Level 24-25
## Objetivo
Un demonio está escuchando en el puerto 30002 y le dará la contraseña de bandit25 si se le proporciona la contraseña de bandit24 y un código PIN numérico secreto de 4 dígitos. No hay forma de recuperar el código PIN, excepto pasando por todas las 10000 combinaciones, lo que se conoce como fuerza bruta.

## Datos de acceso
bandit.labs.overthewire.org
bandit25
p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

## Solución

``` bash
bandit24@bandit:~$ mkdir -p /tmp/pass
bandit24@bandit:~$ cd /tmp/pass
bandit24@bandit:/tmp/secttp$ touch pasword.py
bandit24@bandit:/tmp/secttp$ nano password.py
bandit24@bandit:/tmp/pass$ ./password.py
-bash: ./password.py: Permission denied
bandit24@bandit:/tmp/pass$ python ./password.py
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.

Wrong PINCODE: 0000
Wrong PINCODE: 0001
Wrong PINCODE: 0002
Wrong PINCODE: 0003
Wrong PINCODE: 0004
Wrong PINCODE: 0005
Wrong PINCODE: 0006
Wrong PINCODE: 0007
...
Wrong PINCODE: 2645  
Wrong PINCODE: 2646  
Wrong PINCODE: 2647
Correct!  
The password of user bandit25 is **p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d**
```

## Notas adicionales

## Referencias