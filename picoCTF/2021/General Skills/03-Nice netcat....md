# Nice netcat
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 21135`, but it doesn't speak English...

Hints:
You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

## Solución
Utilizando el comando dado, este nos devuelve una serie de numeros, estos son al parecer son digitos ASCII, creando un programa en python, agregar la serie en un arreglo podemos obtener la bandera
``` bash
holiwiscach@ubuntu:~$ nc mercury.picoctf.net 21135
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
97 
102 
100 
53 
102 
100 
97 
52 
125 
10 

```

Archivo .py donde almacenamos la serie de numeros en el arreglo, y creando una variable vacía **flags**, podemos concatenar los caracteres ASCIIa texto con **chr**
``` python

def get_falg():

	flag = ""

	for index in acsii:
		flag+=chr(index)

	return flag

acssi = [
	112, 
105 ,
99 ,
111 ,
67 ,
84 ,
70 ,
123 ,
103 ,
48 ,
48 ,
100 ,
95 ,
107 ,
49 ,
116 ,
116 ,
121 ,
33 ,
95 ,
110 ,
49 ,
99 ,
51 ,
95 ,
107 ,
49 ,
116 ,
116 ,
121 ,
33 ,
95 ,
97 ,
102 ,
100 ,
53 ,
102 ,
100 ,
97 ,
52 ,
125 ,
10 	 
]

print(get_flag())


```

guardamos u corremos el programa.
``` bash
holiwiscach@ubuntu:~$ python3 get_flag.py 
picoCTF{g00d_k1tty!_n1c3_k1tty!_afd5fda4}
```

