This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

Hints_
1. How do operating systems know what kind of file it is? (It's not just the ending!
2. Make sure to submit the flag as picoCTF{XXXXX}

## Solución
Una vez descargado el archivo proporcionado por el reto, intentamos abrir el archivo txt, pero hay una serie de caracteres no válidos, entonces, usando el comando **xxd** nos damos cuenta que en la cabecera el archivo en realidad en un extension **.png**

``` bash
holiwiscach@ubuntu:~$ xxd flag.txt 
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 06a1 0000 0260 0802 0000 0085 ad5e  .......`.......^
00000020: 9a00 0000 0173 5247 4200 aece 1ce9 0000  .....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...

```

Sabiendo esto entonces cambiamos la extension del archivo y abrimos nuevamente el archivo.

``` bash
holiwiscach@ubuntu:~$ mv flag.txt flag.png
holiwiscach@ubuntu:~$ open flag.png
```

En la imagen aparecera la bandera.

bandera:
picoCTF{now_you_know_about_extensions}