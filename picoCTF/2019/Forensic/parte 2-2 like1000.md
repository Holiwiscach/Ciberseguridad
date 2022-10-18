This [.tar file](https://jupiter.challenges.picoctf.org/static/52084b5ad360b25f9af83933114324e0/1000.tar) got tarred a lot.

Hints:
1. Try and script this, it'll save you a lot of time

## Solución

Tratando de descomprimir el .tar nos muestra otro .tar con un archivo filler.
``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/forensic$ tar -tf 1000.tar 
999.tar
filler.txt

```

Entonces, suponiendo de que sera asi podemos crear un ciclo que descoprima el archivo hasta final.
``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/forensic$ for index in {1000..1}; do tar -xvf $index.tar; done

```
Al final del ciclo podemos encontrar un archivo el cual contiene la bandera.

``` bash
flag.png
filler.txt
holiwiscach@ubuntu:~/Escritorio/Seguridad/forensic$
```

``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/forensic$ open flag.png
```

bandera:
picoCTF{l0t5_0f_TAR5}