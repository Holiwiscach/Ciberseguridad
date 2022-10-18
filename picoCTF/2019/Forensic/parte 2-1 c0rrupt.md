We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

Hints:
1. Try fixing the file header

## Solución

[file signatures](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbWdseGJTQmhkWE9JeHRUSlp5Y3BheXRFTDJCZ3xBQ3Jtc0trdmRRZDNJUWJ4UldKaXRxbzc3MVpwUGR5Y0E5dnd6c1ZwajdrRlJMc3pRVUh5bFlPbmhtWldfMDJNNjcwb1VvMGlxbV9NWXBod1A4NFZ0LUhFVDhPN3hHT2NpblRMQ3lWb3FqVFlUbUhEUEEyREpEaw&q=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FList_of_file_signatures&v=7zY4VkiWbBI)

El archivo que nos dan esta corrupto, como hace referencia a su nombre
Podemos crear una copia por si nos equivocamos
Abrimos el editor hexadecimal y modificamos los primeros bytes para que coincidan a los de una imagen png
```bash
┌──(kali㉿kali)-[~/…/Actividades/PicoCTF-2019/Forensics/c0rrupt]
└─$ hexeditor fixed
```
teniamos estos bytes
```bash
00000000: 89 65 4e 34 0d 0a b0 aa 00 00 00 0d 43 22 44 52  .eN4........C"DR

```
y los cambiamos
```bash
00000000  89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  43 22 44 52                                       .PNG........C"DR
```
cambiamos **89 65 4e 34 0d 0a** y lo que escribimos fue **89 50 4E 47  0D 0A**
Y guardamos con **Ctrl+x** 
Pero si vemos el tipo de archivo que es nos dice que es data
```bash
┌──(kali㉿kali)-[~/…/Actividades/PicoCTF-2019/Forensics/c0rrupt]
└─$ file fixed   
fixed: data
```
Ahora vemos que en los chunks de datos no coinciden con los de un png, tratamos de corregirlos
volvemos a abrir la herramienta hexeditor y correjimos
```bash
00000000  89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  49 48 44 52                                       .PNG........IHDR
```
ahora sustituimos **43 22** que esta casi al final y lo que escribimos fue **49 48**
Si checamos el tipo de archivo ya nos lo muestra como png, pero si lo abrimos aun no nos muestra una imagen
```bash
┌──(kali㉿kali)-[~/…/Actividades/PicoCTF-2019/Forensics/c0rrupt]
└─$ file fixed     
fixed: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
```
si usamos la herramienta pngcheck nos mostrara donde esta el error
```bash
┌──(kali㉿kali)-[~/…/Actividades/PicoCTF-2019/Forensics/c0rrupt]
└─$ pngcheck fixed 
fixed  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERROR: fixed
```
Es un error de redundancia ciclica, y nos dice que es en el chunk pHYs
Lo tenemos de la siguiente manera
```bash
00000040  00 09 70 48  59 73 AA 00   16 25 00 00  16 25 01 49                                       ..pHYs...%...%.I
```
Ese **AA** lo cambiaremos por **00**
y nos quedara asi
```bash
00000040  00 09 70 48  59 73 00 00   16 25 00 00  16 25 01 49                                       ..pHYs...%...%.I
```
Aun no esta reparado
```bash
┌──(kali㉿kali)-[~/…/Actividades/PicoCTF-2019/Forensics/c0rrupt]
└─$ pngcheck fixed 
fixed  invalid chunk length (too large)
ERROR: fixed
```
Usamos nuevamente la herramienta hexeditor e idintificamos que un **IDAT** se encuentra como **DETx**
Se encuentra aqui
```bash
00000050  52 24 F0 AA  AA FF A5 AB   44 45 54 78  5E EC BD 3F                                       R$......DETx^..?
```
cambiamos **AB   44 45** por **49   44 41** y nos debe quedar asi, pero vemos que el tamaño tambien es grande, asi que debemos de hacer otro cambio
```bash
00000050  52 24 F0 AA  AA FF A5 49   44 41 54 78  5E EC BD 3F                                       R$.....IDATx^..?
```
**AA  AA** lo cambiamos por **00  00** y nos queda asi
```bash
00000050  52 24 F0 00  00 FF A5 49   44 41 54 78  5E EC BD 3F                                       R$.....IDATx^..?
```
Ahora usamos nuevamente la herramienta pngcheck
```bash
┌──(kali㉿kali)-[~PicoCTF-2019/Forensics/c0rrupt]
└─$ pngcheck fixed 
OK: fixed (1642x1095, 24-bit RGB, non-interlaced, 96.3%).
```
Al parecer ya esta arreglada, si la abrimos nos muestra una imagen y legible se encuentra la bandera

bandera:
picoCTF{c0rrupt10n_1847995}