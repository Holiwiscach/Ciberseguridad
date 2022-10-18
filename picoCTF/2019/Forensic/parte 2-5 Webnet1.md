We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

Hints:
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?

## Solución
Hacemos el mismo procedimiento para desencriptar los paquetes TLS
Al analizar vemos que se transfirio una imagen y podemos exportar esa imagen
- Vamos a **File**
- Export Objects
- HTTP...
Ahi est ala imagen, la seleccionamos y le damos en **save**
Despues de guardarla vamos a la terminal y con la herramienta strings vemos el contenido
```bash
┌──(kali㉿kali)-[~/…/Actividades/PicoCTF-2019/Forensics/WebNet1]
└─$ strings vulture.jpg | grep 'picoCTF'
picoCTF{honey.roasted.peanuts}