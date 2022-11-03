Morse code is well known. Can you decrypt this? Download the file [here](https://artifacts.picoctf.net/c/235/morse_chal.wav). Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.

Hints:
1. Audacity is a really good program to analyze morse code audio.

## Solución

[MorseCode Decode](https://morsecode.world/international/decoder/audio-decoder-adaptive.html)

El archivo es un audio dónde se escucha que es un código morse, al usar la página **MorseCode** podemos decifrar el mensaje oculto de este archivo.

``` bash
W H 4 7 H 4 7 H 9 0 D W 2 0 U 9 H 7
```

bandera:
picoCTF{WH47_H47H_90D_W20U9H7}