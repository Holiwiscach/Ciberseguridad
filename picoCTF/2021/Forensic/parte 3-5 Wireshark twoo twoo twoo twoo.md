# Wireshark twoo twoo twoo twoo
Can you find the flag? [shark2.pcapng](https://mercury.picoctf.net/static/7b8e53329b34946177a9b5f2860a0292/shark2.pcapng).

Hints:
- Did you really find _the_ flag?
- Look for traffic that seems suspicious.

## Solución

``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/forensic$ cat bandera.csv | cut -d ","  -f 7 | cut -d " " -f 5 | cut -d "." -f 1
"Info"
cGljb0NU
RntkbnNf
M3hmMWxf
ZnR3X2Rl
YWRiZWVm
fQ==
fQ==

```

``` 
cGljb0NURntkbnNfM3hmMWxfZnR3X2RlYWRiZWVmfQ==
```

``` bash
holiwiscach@ubuntu:~$ echo "cGljb0NURntkbnNfM3hmMWxfZnR3X2RlYWRiZWVmfQ==" | base64 --decode
picoCTF{dns_3xf1l_ftw_deadbeef}
```
