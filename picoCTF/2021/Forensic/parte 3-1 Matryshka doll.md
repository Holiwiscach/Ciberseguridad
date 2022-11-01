# Matryshka doll
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg)

Hints:
1. Wait, you can hide files inside files? But how do you find them?
2. Make sure to submit the flag as picoCTF{XXXXX}

## Solución
Vamos a necesitar instalar binwalk para poder descomprimir los archivos ocultos en el jpg.
``` bash
sudo apt install binwalk
binwalk -e archivo.jpg
```

Instalado podemos ejecutar el comando binwalk 4 veces para poder llegar a la bandera
``` bash
holiwiscach@ubuntu:~/matryshka$ binwalk -e dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378950, uncompressed size: 383938, name: base_images/2_c.jpg
651608        0x9F158         End of Zip archive, footer length: 22

holiwiscach@ubuntu:~/matryshka$ ls
dolls.jpg  _dolls.jpg.extracted
holiwiscach@ubuntu:~/Escritorio/Seguridad/picoCTF/forensic/matryshka$ cd _dolls.jpg.extracted/
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted$ ls
4286C.zip  base_images
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted$ cd base_images/
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images$ ls
2_c.jpg
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images$ binwalk -e 2_c.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196043, uncompressed size: 201445, name: base_images/3_c.jpg
383805        0x5DB3D         End of Zip archive, footer length: 22
383916        0x5DBAC         End of Zip archive, footer length: 22

holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images$ ls
2_c.jpg  _2_c.jpg.extracted
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images$ cd _2_c.jpg.extracted/
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted$ ls
2DD3B.zip  base_images
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted$ cd base_images/
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ ls
3_c.jpg
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ binwalk -e 3_c.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77651, uncompressed size: 79809, name: base_images/4_c.jpg
201423        0x312CF         End of Zip archive, footer length: 22

holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ ls
3_c.jpg  _3_c.jpg.extracted
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ cd _3_c.jpg.extracted/
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted$ cd base_images/
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ binwalk -e 4_c.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 65, uncompressed size: 81, name: flag.txt
79787         0x137AB         End of Zip archive, footer length: 22

holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ ls
4_c.jpg  _4_c.jpg.extracted
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ cd _4_c.jpg.extracted/
holiwiscach@ubuntu:~/matryshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted$ ls
136DA.zip  flag.txt
```

Al abrir el archivo .txt dónde se encuentra la bandera, hay una serie de caracteres que impiden leer la bandera estando en medio de cada letra leíble, entonces, haciendo un código en python podemos quitar esos caracteres para solo obtener los caracteres leibles.

``` python
file = open("flag.txt","rb")
datos = bytearray(file.read())
datos = datos.replace(b'\00',b'')

print(datos)
```


bandera:
picoCTF{4f11048e83ffc7d342a15bd2309b47de}