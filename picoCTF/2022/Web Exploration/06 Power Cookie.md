# Power Cookie
Can you get the flag? Go to this [website](http://saturn.picoctf.net:55287/) and see what you can discover.

Hints:
- Do you know how to modify cookies?

## Solución
Una vez entrando a la página lo primero que se encuentra en un botón, el cuál al apretarlo, te redireccióna a otra página con un texto y en dónde no hay nada más.
Estando en esa página nos dirigimos a las cookies, dónde encontraremos inadmin y en dónde el valor que tiene 0 lo cambiamos a 1, guardamos y refrescamos la página y obtendremos la bandera.

picoCTF{gr4d3_A_c00k13_5d2505be}