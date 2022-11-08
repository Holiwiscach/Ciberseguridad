Unzip this [archive](https://drive.google.com/file/d/15pFs7BTOuJ4jrHZOAHNXfPWunY0K9fGl/view?usp=sharing) and find the file named 'oliver_twist.txt'

## Solución
Al descargar el archivo y descomprimirlo, nos damos cuenta que no existe ningún archivo llamado 'olvider_twist.txt'. Entonces damos a suponer que el archivo esta escondido dentro del directorio great_author, por lo que usando el comando **ls -la** nos muestra los directorios que no son visibles.

Al hacerlo, nos encontramos con una carpeta llamada **.secret**

``` bash
holiwiscach@ubuntu:~/general_skills/find_flag/great_author/adequate_books/more_books$ ls -la
total 1968
drwxrwxr-x 3 holiwiscach holiwiscach    4096 oct  5 22:02 .
drwxrwxr-x 3 holiwiscach holiwiscach    4096 oct  5 22:03 ..
-rw-rw-r-- 1 holiwiscach holiwiscach 2001199 may  1  2022 1023.txt.utf-8
drwxrwxr-x 3 holiwiscach holiwiscach    4096 may 13 15:14 .secret
```

Navegando dentro de ella podemos encontrar el archivo perdido.
``` bash
holiwiscach@ubuntu:~/general_skills/find_flag/great_author/adequate_books/more_books$ cd .secret/
holiwiscach@ubuntu:~/general_skills/find_flag/great_author/adequate_books/more_books/.secret$ ls
deeper_secrets
holiwiscach@ubuntu:~/great_author/adequate_books/more_books/.secret$ cd deeper_secrets/
holiwiscach@ubuntu:~/great_author/adequate_books/more_books/.secret/deeper_secrets$ ls
deepest_secrets
holiwiscach@ubuntu:~/great_author/adequate_books/more_books/.secret/deeper_secrets$ cd deepest_secrets/
holiwiscach@ubuntu:~/Escritorio/Seguridad/meta/general_skills/find_flag/great_author/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ ls
Oliver_Twist.txt
```

bandera:
fl@g{Ch@rRl3$_D1cK3N$}