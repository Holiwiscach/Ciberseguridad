We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

Hints:
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?

## Solución
La llave que nos dan es una llave privada RSA
Analizando vemos que vienen unos paquetes encriptados llamados TLS, cargamos la llave en wireshark
- Vamos en la barra de herramientas al menu **Edit**
- Seleccionamos **Preferences**
- Vamos a la seccion de **Protocols**
- Buscamos el que es **TLS**
- En la parte que dice **RSA keys list** damos click en **Edit...**
- Nos sale una tabla, en la parte de **key file** podemos dar doble click y nos abrira un buscador de archivos
- Buscamos la llave que nos dan en el reto y la cargamos
- Podemos especificar el nombre de salida en la parte de  **TLS debug file**
Ahora nos muestra los paquetes HTTP, si lo seguimos (click secundario>Follow>HTTP Stream) podemos ver la bandera.

bandera:
picoCTF{nongshim.shrimp.crackers}
