# Glory of the Garden
This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.

Hints:
- What is a hex editor?

## Solución
Descargando la imagen **garden** abrimos la terminal de linux. La pista nos dice que es un archivo hexa, entonces, ejecutando el comando **hexeditor** y el archivo **garden.jpg** nos mostrara una matriz con hexadecimal, abajo en la terminal tenemos herramientas y el cual nos interesa es Control+w, este comando nos ayuda a buscar entre hexadecimal textos, si buscamos **"picoCTF"** encontraremos la badnera.

``` bash
holiwiscach@ubuntu:~$ hexeditor garden.jpg 
```

En el buscador de string agregamos al campo "picoCTF".

``` bash 
00230560  72 65 20 69  73 20 61 20   66 6C 61 67  20 22 70 69   re is a flag "pi
00230570  63 6F 43 54  46 7B 6D 6F   72 65 5F 74  68 61 6E 5F   coCTF{more_than_
00230580  6D 33 33 74  73 5F 74 68   65 5F 33 79  33 33 64 64   m33ts_the_3y33dd
00230590  32 65 45 46  35 7D 22 0A                              2eEF5}".

```

bandera:
picoCTF{more_than_m33ts_the_3y33dd2eEF5}