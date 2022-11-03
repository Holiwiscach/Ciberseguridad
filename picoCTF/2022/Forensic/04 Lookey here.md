Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/294/anthem.flag.txt).

Hints:
1. Download the file and search for the flag based on the known prefix.

## Solución

``` bash
holiwiscach@ubuntu:~/lookey_here$ cat anthem.flag.txt | grep 'picoCTF'
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}

```

bandera:
picoCTF{gr3p_15_@w3s0m3_4c479940}