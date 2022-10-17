I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt) is all blank!

Hints:

## Solución

Instalamos algunos paquetes python

``` bash
python3 -m pip install pwntools

```

Una vez instalados creamos un archivo python temporal.
``` bash
holiwiscach@ubuntu:~$ nano ex.py

```

Haremos un código que replace los caracteres (en este caso espacios) '\xe2\x80\x83' y '\x20' por 0's y 1's, después decodificamos y obtendremos la bandera.
``` python
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')

data = data.decode('ascii')
data = unbits(data)

print(data)

```

``` bash
holiwiscach@ubuntu:~$ python3 ex.py 
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}\n\t\t'

```

bandera:
picoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}