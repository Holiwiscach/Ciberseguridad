# fixme1.py
Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/37/fixme1.py)
Hints:
- Indentation is very meaningful in Python
- To view the file in the webshell, do: `$ nano fixme1.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Editamos el archivo fixme1.py, en el código hay un error de orientacion en el print con un espacio extra al inicio de la linea, eliminando ese espacio se guarda el archivo y corremos el archivo .py
``` bash
holiwiscach@ubuntu:~$ python3 fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}
```