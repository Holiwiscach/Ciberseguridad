# plumbing
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.

Hints:
- Remember the flag format is picoCTF{XXXX}
- What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)

## Solución
Al ejecutar el comando sale muchas lineas que no ayudan en nada, como nos conectamos hacemos uso de un pipe (|) para usar un grep y que solo nos muestre lo que buscamos
 ``` bash
 holiwiscach@ubuntu:~$ nc jupiter.challenges.picoctf.org 4427 | grep 'picoCTF'
picoCTF{digital_plumb3r_5ea1fbd7}

```