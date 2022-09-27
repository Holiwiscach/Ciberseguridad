# fixme2.py
Fix the syntax error in the Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/66/fixme2.py)
Hints:
- Are equality and assignment the same symbol?
- To view the file in the webshell, do: `$ nano fixme2.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Editamos el archivo fixme1.py, en el código hay un error de sintaxis en el **if** que verifica si la bandera **'flag'** esta vacía con un signo de asignacion **'='**, esto se corrige agregando un signo igual quedando **'=='**, se guarda el archivo y corremos el archivo .py

``` bash
holiwiscach@ubuntu:~$ python3 fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```

picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}