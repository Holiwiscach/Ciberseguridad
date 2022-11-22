Before being captured, our informant told us the following: "To get to base #64 you must make 30 laps in a row"

## Solución
Haciendo un código en python que decodefique 30 veces en base64 el texto para así obtener la bandera.
``` python
import base64

file = open("hackme.txt","r").readline()

data = ''

for i in range(0,len(file)):
	data+= file[i]

for j in range(0,30):
	base64_bytes = data.encode('ascii')
	message_bytes = base64.b64decode(base64_bytes)
	data = message_bytes.decode('ascii')
	
print(data)
```
Bandera:
flag{BASE64_BEST_ENCODE}