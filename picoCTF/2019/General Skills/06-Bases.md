# Bases
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

Hints:
- Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solución
Usando la terminal agregamos la cadena y lo pasamos a base64 desencpriptandola
``` bash
holiwiscach@ubuntu:~$ echo bDNhcm5fdGgzX3IwcDM1 | base64 -d
l3arn_th3_r0p35
```