Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/81c7862241faf4a48bd64a858392c92b/shark1.pcapng).

## Solución

[CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=R3VyIHN5bnQgdmYgY3ZwYlBHU3tjMzN4bm8wMF8xX2YzM19oX3FybnFvcnJzfQ)

Abriendo el archivo nos dirigiremos a los protocolos TCP dónde si seguimos el flujo hasta el 5 nos encontraremos algo

``` bash
Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}
```
Un cifrado que parece estar en ROT13. Para decifrar la bandera nos vamos a la página de **CyberChef** y escogemos la opción de ROT13.

```
The flag is picoCTF{p33kab00_1_s33_u_deadbeef}
```

bandera:
picoCTF{p33kab00_1_s33_u_deadbeef}