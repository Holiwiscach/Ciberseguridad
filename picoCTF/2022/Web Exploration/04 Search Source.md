# Search Source
The developer of this website mistakenly left an important artifact in the website source, can you find it? The website is [here](http://saturn.picoctf.net:58133/)

Hints:
- How could you mirror the website on your local machine so you could use more powerful tools for searching?

## Solución

al analizarlo nos aparece un mensaje como el siguiente:
```html
 <!-- six_box
            end six_box   The flag is not here but keep digging :)-- >
```
Entonces si vamos al archivo **style.css**, y analizamon un poco mas, encontramos en la seccion del header un comentario como el siguiente:
```css
/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/
```
Y podemos apreciar que aqui se encuentra la bandera