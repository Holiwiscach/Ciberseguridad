Can you reverse this [Windows Binary](https://jupiter.challenges.picoctf.org/static/0ef5d0d6d552cd5e0bd60c2adbddaa94/win-exec-1.exe)?

Hints:
1. Microsoft provides windows virtual machines https://developer.microsoft.com/en-us/windows/downloads/virtual-machines
2. Ollydbg may be helpful
3. Flag format: PICOCTF{XXXX}

## Solución

``` bash
sudo dpkg --add-architecture i386
sudo apt install wine
sudo apt install wine32:i386

```

Ejecutamos el archivo con wine
``` bash
holiwiscach@ubuntu:~/b1ll_g4t3s$ wine win-exec-1.exe 
Input a number between 1 and 5 digits: 123
Initializing...
Enter the correct key to get the access codes: 123
Incorrect key. Try again.

```
Vemos que es imporible el acceso hacia la bandera, por lo que abrimos el programa ghidra para ver el código. Una vez dentro buscamos algún caracter que nos haga dirigirnos a la función main (en este caso between).

![[Pasted image 20221119152223.png]]
Encontrando coincidencia logramos encontrar el código en la aprte que nos da la bandera.
Leyendolo hay una condición la cual nos pide la clave previamente, si cambiamos la estructura del código ensamblador podemos saltarnos esa parte y que nos de la bandera haciendo cambios en el path (justamente en JNZ por JNC).
![[Pasted image 20221119151113.png]]

![[Pasted image 20221119151319.png]]

Importamos el archivo modificado como binario, después hecho le quitamos la extención binario y ejecutamos nuevamente.
``` bash
holiwiscach@ubuntu:~$ mv win-exec-2.exe.bin win-exec-2.exe
holiwiscach@ubuntu:~$ wine win-exec-2.exe 
Input a number between 1 and 5 digits: 1
Initializing...
Enter the correct key to get the access codes: 12
Correct input. Printing flag: PICOCTF{These are the access codes to the vault: 1063340}
```

bandera:
PICOCTF{These are the access codes to the vault: 1063340}