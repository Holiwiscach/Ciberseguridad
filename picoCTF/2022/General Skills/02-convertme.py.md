# converme.py
Run the Python script and convert the given number from decimal to binary to get the flag. [Download Python script](https://artifacts.picoctf.net/c/32/convertme.py)

Hints:
- Look up a decimal to binary number conversion app on the web or use your computer's calculator!
- The `str_xor` function does not need to be reverse engineered for this challenge.
- If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
- To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
- Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
- Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`

## Solución

El programa nos imprime un numero random en base a decimal y nos pide, ¿Cuaĺ es su base en binario?

Entrando a una página 
[Podemos obtener de numero decimal a numero binario](https://es.convertbinary.com/decimal-a-binario/)

después de obtenet el numero a binario y ponerlo como respuesta en el porgrama nos imprime la bandera.

``` bash
holiwiscach@ubuntu:~$ python3 convertme.py 
If 37 is in decimal base, what is it in binary base?
Answer: 100101
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_722f6b39}

```


picoCTF{4ll_y0ur_b4535_722f6b39}
