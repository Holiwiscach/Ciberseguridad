# Glitch Cat
Our flag printing service has started glitching! `$ nc saturn.picoctf.net 65353`

Hints:
- ASCII is one of the most common encodings used in programming
- We know that the glitch output is valid Python, somehow!
- Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solución
Creando un archivo .py dónde se agrega la cadena de caracteres en binario automaticamente pasa a texto usando **chr**, guardando y corriendo el archivo nos dara la bandera.
``` python
print('That is correct! Here\'s your flag: ' + 'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}')
```

``` bash
holiwiscach@ubuntu:~$ python3 Glitch.py
That is correct! Here's your flag: picoCTF{gl17ch_m3_n07_9c42a45d}
```


picoCTF{gl17ch_m3_n07_9c42a45d}