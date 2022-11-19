The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed).

Hints:
1. What is the final key?

## Solución

Entrando a gdb con el nombre del archivos para poder desensablar el código, especificamente en la parte de la función main
``` bash
(gdb) disassemble main
Dump of assembler code for function main:
   0x000000000000091a <+0>:	push   %rbp
   0x000000000000091b <+1>:	mov    %rsp,%rbp
   0x000000000000091e <+4>:	sub    $0x10,%rsp
   0x0000000000000922 <+8>:	mov    %edi,-0x4(%rbp)
   0x0000000000000925 <+11>:	mov    %rsi,-0x10(%rbp)
   0x0000000000000929 <+15>:	mov    $0x0,%eax
   0x000000000000092e <+20>:	call   0x8d8 <header>
   0x0000000000000933 <+25>:	mov    $0x0,%eax
   0x0000000000000938 <+30>:	call   0x82f <set_timer>
   0x000000000000093d <+35>:	mov    $0x0,%eax
   0x0000000000000942 <+40>:	call   0x87d <get_key>
   0x0000000000000947 <+45>:	mov    $0x0,%eax
   0x000000000000094c <+50>:	call   0x8ac <print_flag>
   0x0000000000000951 <+55>:	mov    $0x0,%eax
   0x0000000000000956 <+60>:	leave  
   0x0000000000000957 <+61>:	ret 
```

Obervamos que en <+30> hay un set_time que es el que nos bloquea al tratar de obtener la bandera, para quitar esa ejecución usamos el comando hexeditor para podernos saltar esas líneas, especificamente en  0x0000000000000938

``` bash
Realizamos cambios 
Original
00000930  FF FF FF B8  00 00 00 00   E8 F2 FE FF  FF B8 00 00

Alterado
00000930  FF FF FF B8  00 00 00 00   90 90 90 90  90 B8 00 00

```

ejecutamos el código ya hora nos entrega la bandera
``` bash
holiwiscach@ubuntu:~/need_for_speed$ ./need-for-speed2
Keep this thing over 50 mph!
============================

Creating key...
Finished
Printing flag:
PICOCTF{Good job keeping bus #190ca38b speeding along!}

```

bandera:
PICOCTF{Good job keeping bus #190ca38b speeding along!}