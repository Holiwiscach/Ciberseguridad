Now you DON’T see me. This [report](https://artifacts.picoctf.net/c/264/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

Hints:
1. How can you be sure of the redaction?

## Solución

Para este reto se inspecciono la página dónde nos muestra el texto cifrado o cubierto.

Siguiendo el siguiente flujo: outerContainer -> mainContainer -> viewerContainer -> viewer -> page -> textLayer. Podemos encontrar los textos que se escibieron en el archivo también descubiertos.

bandera:
picoCTF{C4n_Y0u_S33_m3_fully}