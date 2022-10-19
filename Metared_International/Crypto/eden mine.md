I downloaded one of my friend's files that describe how **frequently** he visits the "eden mine" in Zacatecas, México, but i think there might be more to it.

The most important time of the "eden mine" was during the XVII and XVIII centuries when production was mainly based in silver and gold. Given the floods in its shafts and how close it is to the city, in 1960 the exploitation of the mine ended, a little after it was adapted for tourism, being the most visited mine in the country by national and foreign tourists.

## Solución
Al abrir el archivo encontramos una linea larga con caracteres, analizando los caracteres, vemos que se repiten alguno de ellos, entonces crearemos un archivo python para poder contar los caracteres que hay en la linea.

``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/meta/cypto$ nano edenPy.py

```

``` python
with open("edenmine.txt") as file: #abrimos el archivo txt y nombramos la variable como "file"
        linea = file.readline() #String que almacenara la unica linea obtenida del archivo txt
        datos = [] #Arreglo de datos que almacenara los caracteres diferentes encontrados en la linea.
        flag = "" #Se contaran los caracteres encontrados en la linea y se almacenaran y concanetaran en la variable flag

## Ciclo que recorrera la linea de caracteres y almacenara en datos los caracteres diferentes encontrados.
        for caracter in linea:
                if datos.count(caracter) <1:
                        datos.append(caracter)
## contara los caracteres encontrados
        for caracter in datos:
                flag += str(linea.count(caracter))+" "

print(flag)
```

Al iniciar el programa, obtendremos una serie de numeros el cual, analizandolo es una encriptacion a decimal, desencriptandolo podemos encontrar la bandera.
``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/meta/cypto$ python3 edenPy.py 
102 108 97 103 77 88 123 73 95 49 48 118 51 95 102 114 51 113 117 51 110 99 105 101 115 95 88 68 125 
```

bandera:
flagMX{I_10v3_fr3qu3ncies_XD}