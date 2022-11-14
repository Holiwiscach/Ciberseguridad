Can you get the flag? Download this [binary](https://artifacts.picoctf.net/c/115/gdbme). Here's the test drive instructions:

-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`

## Solución

Intrucciones:
- Da permisos de ejecución al archivo.
- Abrir el archivo con el comando gdb mostrandonos el código ensamblador.
- Establece un punto para poder ejecutar la linea (método main de la línea 99)
- Ejecuta el programa
- Hace un salto para hacer llamar al método main en la línea 104.

bandera:
picoCTF{d3bugg3r_dr1v3_197c378a}