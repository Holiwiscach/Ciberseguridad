We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/393/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

Hints:
1. Do you know what `mod 37` means?
2. `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solución

Abriendo el archivo proporcionado por el reto podemos ver que tenemos una cadena de caracteres.
``` bash
holiwiscach@ubuntu:~/basic_1$ cat message.txt 
54 396 131 198 225 258 87 258 128 211 57 235 114 258 144 220 39 175 330 338 297 288
```

Entonces, aplicando la sugerencia del reto, creamos un programa en python dónde nos haga el trabajo.
``` bash
holiwiscach@ubuntu:~/basic_1$ nano b1.py

```

Abrimos el archivo y lo ponemos en un arreglo, para cada elemento guardado hacemos modulo 37, y condicionamos, si el modulo de 37 salio entre 0 a 25 entonces es una letra del alfabeto en caracter ACSII, si esta entre 26 a 36 entonces es un numero decimal, y si es 36 es un espacio o guion bajo.

``` python
datos = open( 'message.txt' ).read().split() 

flag = '' 
s = ''

for n in datos: 
        c = int(n) % 37 
        if c>=0 and c<=25:
                s = chr(c+65)
        elif c>=26 and c<=35: 
                s = chr(c+22) 
        else: 
                s = '_' 

        flag+=s 

print(f"picoCTF{{{flag}}}")

```

Ejecutando el programa podemos obtener la bandera.
``` bash
holiwiscach@ubuntu:~/basic_1$ python3 b1.py 
picoCTF{R0UND_N_R0UND_79C18FB3}

```

bandera:
picoCTF{R0UND_N_R0UND_79C18FB3}