
## Solución
Abriendo el texto efectivamente solo aparecen espacios en blanco, con un código en python podemos obtener los diferentes tipos de espacios que puede haber con bytearray. Analizando el texto en bytes podemos remplazar los caracteres por 0 y 1, y decodificandolo podemos obtener la bandera.

``` python
file = open("space_encoded.txt","rb").readlines()

flag = ''
for i in range(0,len(file)):
	data = bytearray(file[i])
	
	data = data.replace(b'\x20',b'0')
	data = data.replace(b'\t',b'1')
	data = data.replace(b'\r',b'0')
	data = data.replace(b'\n',b'1')
	
	data = data.decode('ascii')
	
	flag+= chr(int(data[:8], 2))


print(flag)
```

bandera:
flag{ESPACIO_EXTERIOR}