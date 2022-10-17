# MacroHard WeakEdge
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/2e739f9e0dc9f4c1556ea6b033c3ec8e/Forensics is fun.pptm)


## Solución
Deccargando el archivo dado, lo podemos descomprimir en una carpeta vacía.

``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad$ mkdir forensic
holiwiscach@ubuntu:~/Escritorio/Seguridad$ cd forensic/
holiwiscach@ubuntu:~/Escritorio/Seguridad/forensic$ unzip Forensics\ is\ fun.pptm 

```
Hay muchos directorios, y para poder navegar en ellos sin perdernos podemos usar el editor de texto Visual Code.
Navegando entre los directorios encontraremos un archivo **hidden**, donde este archivo no tiene extensión y se encuentra en ppt -> silderMasters -> rels. Abriendo el archivo se encontrara una cadena de caracteres el cual contiene la bandera encriptada.

contenido:
"Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q"

Para obtener la bandera podemos usar la terminar para ejecutar algunos comandos para poder desencriptar y obtener la badnera.

``` bash
holiwiscach@ubuntu:~$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " " | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: entrada inválida

```

Indicamos que imprima en la consola la serie de caracteres, pero omitira los espacios agrupandolos, después usamos el comando base64 para desencriptar y listo.

picoCTF{D1d_u_kn0w_ppts_r_z1p5}