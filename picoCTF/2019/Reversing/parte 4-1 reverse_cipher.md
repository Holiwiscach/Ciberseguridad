We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). Can you reverse the flag.

Hints:
1. objdump and Gihdra are some tools that could assist with this

## Solución
Abrimos la aplicación ghidra e importamos el archivo rev. Una vez abierto, trataremos de buscar el método main en la carpeta funtion de Symbol Tree.

![[Pasted image 20221119142928.png]]

Apreciarmos que nos dara el código de main en lenguaje C, leyendolo podemos observar que hay un ciclo for y una condición dentro de ella donde dice que si el caracter de la bandera en par entonces le suma 5, en caso contrario le resta 2.
Entonces si hacemos lo contrario podemos ver el cifrado de la bandera haciendo un código en python.

``` python
cifrado = open('rev_this',"r").read()

print(cifrado)

flag=''

for i in range(0,len(cifrado)-1):
	if i & 1 == 0:
		flag+=chr( ord(cifrado[i]) - 5 )
	else:
		flag+=chr( ord(cifrado[i]) + 2 )

print(flag)

```
Ejecutamos el código y nos suelta la bandera decifrada.

bandera:
picoCTF{r3v3rs312528e05}