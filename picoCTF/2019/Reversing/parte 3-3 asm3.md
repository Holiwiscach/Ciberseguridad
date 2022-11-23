What does asm3(0xba6c5a02,0xd101e3dd,0xbb86a173) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S)

Hints:
1. more(?) [registers](https://wiki.skullsecurity.org/index.php?title=Registers)

## Solución

[Guía ensamblador x86](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html)

[Emulador ensamblador](https://carlosrafaelgn.com.br/Asm86/)

No se encontro solución a este reto, se intento hacerlo de la siguiente manera

Se creo una copia de test.S dónde le quita los **":"** y solo nos quedamos con el código, todo eso se le asignara al archivo nombrado chal.s
``` bash
holiwiscach@ubuntu:~/asm3$ cat test.S | cut -d ":" -f2 > chal.s

```
Editamos el archivo chal.s para agregarle que se usara intel y que se llamara de manera global
``` bash
.intel_syntax noprefix
.global asm3

asm3:
        push   ebp
        mov    ebp,esp
        xor    eax,eax
        mov    ah,BYTE PTR [ebp+0xb]
        shl    ax,0x10
        sub    al,BYTE PTR [ebp+0xd]
        add    ah,BYTE PTR [ebp+0xc]
        xor    ax,WORD PTR [ebp+0x12]
        nop
        pop    ebp
        ret  
```

Después se crea un archivo solve.c que ejecutara el ensamblador.
``` c
#include <stdio.h>

int main(){
	printf("flag: 0x%x \n", asm3("0xba6c5a02","0xd101e3dd","0xbb86a173"));
}
```

Hacemos que el código en C y el ensamblador nos devuelban el resultado en un archivo aparte el cual llamaremos **a.out**

``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/picoCTF/reversing/asm3$ gcc -m32 -c chal.s -o chal.o
holiwiscach@ubuntu:~/Escritorio/Seguridad/picoCTF/reversing/asm3$ gcc -m32 -c solve.c -o solve.o -w
holiwiscach@ubuntu:~/Escritorio/Seguridad/picoCTF/reversing/asm3$ gcc -m32 -o a.out solve.o chal.o
holiwiscach@ubuntu:~/Escritorio/Seguridad/picoCTF/reversing/asm3$ ./a.out 
flag: 0x45c7 

```

Sin embargo, la bandera que nos esta lanzando es incorrecta.
Se intento también hacerlo desde un simulador de lenguaje ensamblador, pero al ejecutar el código nos sale un error.

