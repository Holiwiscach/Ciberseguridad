Can you get the flag? Run this [Python program](https://artifacts.picoctf.net/c/428/bloat.flag.py) in the same directory as this [encrypted flag](https://artifacts.picoctf.net/c/428/flag.txt.enc).

## Solución

Código de python abierto
``` python
import sys

a = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ"+ \

"[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~ "
  

def arg133(arg432):

if arg432 == a[71]+a[64]+a[79]+a[79]+a[88]+a[66]+a[71]+a[64]+a[77]+a[66]+a[68]:

return True

else:

print(a[51]+a[71]+a[64]+a[83]+a[94]+a[79]+a[64]+a[82]+a[82]+a[86]+a[78]+\

a[81]+a[67]+a[94]+a[72]+a[82]+a[94]+a[72]+a[77]+a[66]+a[78]+a[81]+\

a[81]+a[68]+a[66]+a[83])

sys.exit(0)

return False

def arg111(arg444):

return arg122(arg444.decode(), a[81]+a[64]+a[79]+a[82]+a[66]+a[64]+a[75]+\

a[75]+a[72]+a[78]+a[77])

def arg232():

return input(a[47]+a[75]+a[68]+a[64]+a[82]+a[68]+a[94]+a[68]+a[77]+a[83]+\

a[68]+a[81]+a[94]+a[66]+a[78]+a[81]+a[81]+a[68]+a[66]+a[83]+\

a[94]+a[79]+a[64]+a[82]+a[82]+a[86]+a[78]+a[81]+a[67]+a[94]+\

a[69]+a[78]+a[81]+a[94]+a[69]+a[75]+a[64]+a[70]+a[25]+a[94])

def arg132():

return open('flag.txt.enc', 'rb').read()

def arg112():

print(a[54]+a[68]+a[75]+a[66]+a[78]+a[76]+a[68]+a[94]+a[65]+a[64]+a[66]+\

a[74]+a[13]+a[13]+a[13]+a[94]+a[88]+a[78]+a[84]+a[81]+a[94]+a[69]+\

a[75]+a[64]+a[70]+a[11]+a[94]+a[84]+a[82]+a[68]+a[81]+a[25])

def arg122(arg432, arg423):

arg433 = arg423

i = 0

while len(arg433) < len(arg432):

arg433 = arg433 + arg423[i]

i = (i + 1) % len(arg423)

return "".join([chr(ord(arg422) ^ ord(arg442)) for (arg422,arg442) in zip(arg432,arg433)])

arg444 = arg132()

arg432 = arg232()

arg133(arg432)

arg112()

arg423 = arg111(arg444)

print(arg423)

sys.exit(0)
```

Al analizarlo detalladamente, podemos ver que hay una secuencia, con ella y sabiendo un poco sobre python podemos darnos cuenta el valo que retorna o imprime cada método.
``` python 
arg444 = arg132() # Lee el archivo que contiene la bandera encriptada

arg432 = arg232() #Muestra un mensaje al usuario y pide que ingrese un password

arg133(arg432) #Compara la cadena escrita por el usuario por otra en especifico -------- parte que nos interesa

arg112()

arg423 = arg111(arg444)

print(arg423)
```

En el método podemos ver que compara la cadena password ingresada con el usuario por una cadena de caracteres especifica, lo que podemos hacer es tomarla y ponerla al principio de el proceso de intrucciones.
```python
print(a[71]+a[64]+a[79]+a[79]+a[88]+a[66]+a[71]+a[64]+a[77]+a[66]+a[68]) #Línea agregada la cuál contiene el password de usuario.

arg444 = arg132()

arg432 = arg232()

arg133(arg432)

arg112()

arg423 = arg111(arg444)

print(arg423)
```

Compilamos el código y nos mostrara el password para ingresar y obtener la bandera.
``` bash
holiwiscach@ubuntu:~/bloat$ python3 bloat.flag.py 
happychance
Please enter correct password for flag: happychance
Welcome back... your flag, user:
picoCTF{d30bfu5c4710n_f7w_b8062eec}
```

bandera:
picoCTF{d30bfu5c4710n_f7w_b8062eec}