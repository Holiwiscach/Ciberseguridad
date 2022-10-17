We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

Hints:
1. Try using a tool like Wireshark
2. What are streams?

## Solución 
Una vez descargado el archivo que nos proporciona el reto, abrimos la terminal y usamos el comando wireshark.

``` bash
holiwiscach@ubuntu:~$ wireshark

```

Estando en la aplicación, abrimos el archivo que descargamos del reto, buscamos entre los protocolos **UDP** haciendo en uno de ellos click derecho -> seguir -> flujo UDP, estando buscando entre ellos encontraremos la bandera.

bandera:
picoCTF{StaT31355_636f6e6e}