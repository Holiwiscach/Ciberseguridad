Can you get the flag? Reverse engineer this [Python program](https://artifacts.picoctf.net/c/464/unpackme.flag.py).

## Solución

``` python
import base64

from cryptography.fernet import Fernet

payload = b'gAAAAABiMD04m0Z6CohVV7ozdwHqtgc2__CuAFGG8rWhZBTL0lhfzp-mhu9LYNMnMQMGO-7tEwy3DJ2Y8yjogvzyojFETwN9YEIPXTnO9F1QnkPypWTgjISGve4gcSerJMs694oKcIdKHuVaSxOg1MMNs5k9iPaBIPU7xOKQqCyhnf_f4yUvLdMcer38BqRptocJNvKlyWN8h7ikoWL0zlssxd8OJyPujMz78HZaefvUouvq6LDtPVqRBJFPgSJYf1nHpHKFa1O0zJ6UpTe6ba3PPAxCVXutNg=='

  

key_str = 'correctstaplecorrectstaplecorrec'

key_base64 = base64.b64encode(key_str.encode())

f = Fernet(key_base64)

plain = f.decrypt(payload)

print(f.decrypt(payload)) #Línea agregada para imprimir lo que guarda en la variable pyload ya desencriptada.

exec(plain.decode())
```

Ejecutamos el código y observamos que de hecho, playload son líneas de código de python la cuál nos pide un password y compara una passwors especifico **"batteryhorse"** con la entrada dada por el usuario y mostrandonos la bandera.
``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/picoCTF/reversing/unpackme$ python3 unpackme.flag.py 
b"\npw = input('What\\'s the password? ')\n\nif pw == 'batteryhorse':\n  print('picoCTF{175_chr157m45_5274ff21}')\nelse:\n  print('That password is incorrect.')\n\n"
What's the password? batteryhorse
picoCTF{175_chr157m45_5274ff21}

```

bandera:
picoCTF{175_chr157m45_5274ff21}
