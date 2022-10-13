# Includes
Can you get the flag? Go to this [website](http://saturn.picoctf.net:54634/) and see what you can discover.

Hints:
- Is there more code than what the inspector initially shows?

## Solución
Entrando a la página lo que se tiene que hacer es inspeccionar el codigo fuente de la web. Una vez dentro podemos darnos cuenta que podemos ver los archivos **style.css** y **script.js**.

Dentro de styles.css encontraremos la primera parte de la bandera
``` css
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */

```

y dentro de scipt.js encontrarmos la segunda parte

``` js
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_df589022}
```

Bandera:

picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}