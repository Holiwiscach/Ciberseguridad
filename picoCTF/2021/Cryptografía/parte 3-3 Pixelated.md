I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled2.png)

Hints:
1. [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
2. Think of different ways you can "stack" images

## Solución

Para solucionar este reto vamos a crear un programa en python que ponga los pixeles en arreglos.
``` bash
holiwiscach@ubuntu:~/Pixed$ nano pixed.py

```

Creamos el código, donde obtenemos los pixeles de las imagenes para despues juntarlas y hacer una nueva imagen
``` python
from PIL import Image
import numpy as np

imagen1 = np.asarray( Image.open('scrambled1.png') )
imagen2 = np.asarray( Image.open('scrambled2.png') )

datos = imagen1.copy() + imagen2.copy()

nueva = Image.fromarray(datos)

nueva.save('nueva.png','PNG')


```

Ejecutando el programa nos creara una nueva imagen **nueva.png** el cuál tiene la bandera.
``` bash
holiwiscach@ubuntu:~/Pixed$ python3 pixed.py 
holiwiscach@ubuntu:~/Pixed$ open nueva.png 
```

bandera:
picoCTF{d72ea4af}