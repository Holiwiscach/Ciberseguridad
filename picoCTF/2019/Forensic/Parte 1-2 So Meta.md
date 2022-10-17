Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).

Hints:
1. What does meta mean in the context of files?
2. Ever heard of metadata?

## Solución
Una vez descargado la imágen que nos proporciona el reto, abrimos la terminal y usamos el comando **exiftool**, este comando nos ayuda a saber información meta (dimension del archivo, la hora dónde se tomó, la hora, quién tomó la foto, etc... ).

``` bash
holiwiscach@ubuntu:~$ exiftool pico_img.png 
```

``` bash
...
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_d8944929}
Image Size                      : 600x600
Megapixels                      : 0.360

```

bandera:
picoCTF{s0_m3ta_d8944929}