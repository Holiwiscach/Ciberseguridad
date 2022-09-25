# Level 16-17
## Objetivo
Las credenciales para el siguiente nivel se pueden recuperar enviando la contraseña del nivel actual a un puerto en localhost en el rango de 31000 a 32000. Primero averigüe cuál de estos puertos tiene un servidor escuchando en ellos. Luego, averigüe cuáles de ellos hablan SSL y cuáles no. Solo hay 1 servidor que proporcionará las siguientes credenciales, los demás simplemente le enviarán lo que le envíe.

## Datos de acceso
bandit.labs.overthewire.org
bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

## Solución
``` bash
bandit16@bandit:~$ nmap -A localhost -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2022-09-08 14:45 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00021s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE     VERSION
31046/tcp open  echo
31518/tcp open  ssl/echo
31691/tcp open  echo
31790/tcp open  ssl/unknown
31960/tcp open  echo

bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  8 10:01:29 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  8 10:01:29 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  8 10:00:29 2022 GMT; NotAfter: Sep  8 10:01:29 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEJ67pnTANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTA4MTAwMDI5WhcNMjIwOTA4MTAwMTI5WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDO
XGNf9z7fhkdcTvEGi4F+3ziW3S+C+b2PmgOPSnkbsmraJW8oUoSrJPuyMEczcr1i
eyCAfA/uaaA4RWUgVqkU+x6lfmiOGNaxz75H1DlOglKknRfefERn3h1gxolZC/Fv
pOVWOj4q8kTb3gjdn4ozMxfExH+bmHxNqDxrNFS4oU25RvJj3OzJ7Q+i4PFKwZHY
j3nmeSu5KNJ7ppyc70Ud94VAogzL8FqWMqa0FXoDN2XBaLODvYPP70rL3TJF+8FI
EQbmd8MrQ/FDJFWi36WT5R4Kw6nqgHvcsl+ZISrZFPcL+T/c698pMx2OnJprkdQC
N8LGBct+qDABF3u/LhcxAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQC+
HJHN32/NP10OZ1jiwvufpt0spTciishlhETTDgwQxcPQj1+pocG/VD4U9ywMK+As
Ds1Hrq/xet3158kuJ95ZoKhq+ZuUyUXNfYi0bNiXyBCc2KiVQd6oUCCcCPtHxwss
S18/rbI5RicvygFgrez4BLu8NUuxxu4sk93eUgyo4g6IC5yY9seG5eNn++/Jsfil
XTBoFTqE82cYgP2JDLV5MlbXzhqC4LUUQS3ZL7pNXJuR+Na5H/35b76vj6DPuqn4
vCkWUZQyJDY0cNQ3NhmxZsYvIauZwKz2fttdTaT7UAXwnOdrOWyVVYm9IlzmWiZq
rNYmPm5D7is9KAvoClXL
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: EBBE013D9C3B2FC5178339CDF84D3C4465562D42B87BF2EF2B0D8DC7D9094441
    Session-ID-ctx: 
    Resumption PSK: C2661CB8714347A9D2B38396098B0FC8AD700142D1925E838C672C39445BA451736CBD9566BDA84420FE39B0B9109B59
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fb 71 d2 41 ec 1b cc c0-e3 b2 43 3f f7 a6 76 e3   .q.A......C?..v.
    0010 - dc 98 58 82 6c 45 0b a4-cd bb 38 1e 3b 65 ea 42   ..X.lE....8.;e.B
    0020 - 4e 5c 33 9f ce e1 09 9b-5b c8 b9 7a 3a 0a c3 15   N\3.....[..z:...
    0030 - 84 8d 60 40 af f2 13 8a-f1 44 57 c2 f8 ea 10 95   ..`@.....DW.....
    0040 - c6 c3 36 29 0f 98 4d 8b-b9 5b 23 57 5d d7 cc 6a   ..6)..M..[#W]..j
    0050 - ae 6f 5a 03 4e 9e e7 1f-8c bc 0f aa c3 e6 d5 e4   .oZ.N...........
    0060 - 78 fe d4 79 04 52 c2 68-65 63 3e 31 f8 6b 8a a2   x..y.R.hec>1.k..
    0070 - 3c f3 6c 78 c9 fc a9 55-e9 f2 a8 a5 ad f1 f5 27   <.lx...U.......'
    0080 - cb 23 60 7c 59 3c b2 ac-0d 6f 0f b4 40 2a 15 44   .#`|Y<...o..@*.D
    0090 - 98 3d 2d b7 66 e1 e4 db-4a 13 3d 91 85 7f 27 5b   .=-.f...J.=...'[
    00a0 - e0 78 b7 13 10 79 9e 0d-51 07 1d f3 eb a0 4b d8   .x...y..Q.....K.
    00b0 - e2 fa 19 3e cf a2 56 bb-76 56 02 55 d6 bb 2e 42   ...>..V.vV.U...B
    00c0 - 9f 34 3d 0d aa 94 7a 19-98 7a fa dd 8a 62 cf 9f   .4=...z..z...b..

    Start Time: 1662648859
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 00A97427747764EE1A47AF4C6BDF49645DF5C1745273E42BC01D8DAB2AFD126B
    Session-ID-ctx: 
    Resumption PSK: 73CBB093D8F7740152C3CFC15A93E77EB63267439F6C47FC779FB795361D659E12BA510B627EA22B0DCA80718285DE3E
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fb 71 d2 41 ec 1b cc c0-e3 b2 43 3f f7 a6 76 e3   .q.A......C?..v.
    0010 - ea 8b 7d 19 b3 69 9d ad-43 f9 64 83 ff aa 3e 29   ..}..i..C.d...>)
    0020 - ed e0 02 c5 8c ff e6 2d-77 f6 cb fc c6 69 0c 22   .......-w....i."
    0030 - f8 81 70 6e 13 6c 1c 6b-3b 41 a4 04 02 99 da dd   ..pn.l.k;A......
    0040 - e2 a0 c0 c9 6d 41 70 4a-22 9a b1 e0 1e 24 f2 c0   ....mApJ"....$..
    0050 - 56 45 75 29 d7 48 2a df-73 41 85 36 7c 5a 80 1e   VEu).H*.sA.6|Z..
    0060 - 74 71 8e c9 85 3a 3d 7d-aa 2c 9e 8d 53 19 7a 9b   tq...:=}.,..S.z.
    0070 - 88 74 86 76 03 ee 05 73-59 a8 a2 22 21 ab 9f 52   .t.v...sY.."!..R
    0080 - 18 aa 73 15 e5 08 7b 31-a2 7a 91 dc 5e 76 f0 b5   ..s...{1.z..^v..
    0090 - 5c c8 6a 37 9f 0e 3d 5c-6f f8 8c ba 0f 7f 19 72   \.j7..=\o......r
    00a0 - 60 42 86 10 04 f1 d0 51-02 64 e1 aa f3 27 ed 6a   `B.....Q.d...'.j
    00b0 - ae 1e 26 d4 a5 89 1e 36-41 02 49 86 88 c7 2c 54   ..&....6A.I...,T
    00c0 - e6 78 be 94 10 8b 69 b3-d3 e5 59 79 b4 62 64 0d   .x....i...Yy.bd.

    Start Time: 1662648859
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$ logout
Connection to bandit.labs.overthewire.org closed.
holiwiscach@ubuntu:~$ nano llave
holiwiscach@ubuntu:~$ chmod 600 llave
holiwiscach@ubuntu:~$ ssh -i llave bandit17@bandit.labs.overthewire.org -p 2220

bandit17@bandit:~$ cat /etc/bandit_pass/bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
bandit17@bandit:~$ 

```

## Notas adicionales
- **nmap** realizar funciones de auditoría y seguridad de redes, rastreo y análisis en busca de sistemas para elaborar un inventario de red
- **chmod** cambia los permisos de un archivo o carpeta.

## Referencias
[Port scanner on Wikipedia](https://en.wikipedia.org/wiki/Port_scanner)
