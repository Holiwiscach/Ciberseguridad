# Forbidden Paths
Can you get the flag? Here's the [website](http://saturn.picoctf.net:49700/). We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

Hints:

## Solución

Estando en la página, nos muestra nombres de archivos de texto que podemos insertar en el campo, algo curioso es que al principio del texto hay dos puntos.
Al ponerlo en el campo de texto no sucede ningún error, si se intenta hacer un control de estructuras de archivos podemos encontrar la bandera.

```
../../../../flag.txt
```

Bandera:
picoCTF{7h3_p47h_70_5ucc355_6db46514}