# Level 15-16
## Objetivo
La clave para el siguiente nivel  se puede recuperar enviando la contraseña actual del nivel al puerto actual 30001 en localhost usando encriptacion SSL.

Nota uitl: ¿Obtienes "HEARTBEATING" y "Read R BLOCK? Use -ign_eof y lea la seccion "COMANDOS CONECTADOS" en la pagina de manual. Junto a 'R' y 'Q', el comando 'B' tambien funciona en esta version de ese comando...

## Datos de acceso
bandit.labs.overthewire.org
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solución
``` bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  8 10:03:30 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  8 10:03:30 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  8 10:02:30 2022 GMT; NotAfter: Sep  8 10:03:30 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEWSCiUjANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTA4MTAwMjMwWhcNMjIwOTA4MTAwMzMwWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCk
XDu4H6Iyiy4h52QKXDRK1xKysta7xIaPetYfSBmyha6R5GXf97S0aIDLXD9vSxeM
nGeEsLsnSpxASbgSp3V4CMWPbWYGSAPpR+lR4rYGHcR+yaLGaUik4pZy4W9EFks3
N+umNPwhdhkxT22PJjD447yLgXR/ps8um0F4HnDCuZsylUy8tpTI7EWE+7YZTlEE
CVazFFQf/x37rVQvGrC0xFhz5BVD3QyTD9CqhsGFUJn6/4TAYWRe2j4ckE2rDgpz
ltiY5UF7X5yKCDDj/EHrB35eMMw/wcD/V/oOvLOiRhsvxSl5tul2lzvEUtV0LIkq
JVw3wWy7Z55DxNZemXCdAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAi
ZfZU5k65BFpIpQYa116x1tX7+TvjIst+jDq6+FVS3el0b4R8CL6gk2lG/gQ/E9MK
noLPXO6wfONkidV4gFZqnVqGp6+ktW52kO4CXt6X4bzBPqmrjpOIg9utsgp43gk9
Zj4pY/46hepiesM4Iz8j1uvY9L1gq3/dFz0Ysh9+EAVdS6mzYCW2+6I+fidYldbd
ZiGouAm73aqV3CiHl3xHQ3quLkhgNO7EnwPhQp65c0Y5UhXLWuiCnQCZheoV0AmK
/DDJIQ3RIlCuU1I4fqqs+MkU6sYfx4bTjhCZvd4S2QfxyoqOCo0dfNrc1qcBwq2h
N8Rw6xCEouyQpWN1670Y
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
    Session-ID: C66476FEFD1147A752C89EEC6158D5875B6C9B4BCEB8F643E4A6AE53E38FEF1D
    Session-ID-ctx: 
    Resumption PSK: 1BE4F51129B27D11062174C7E4B2BB8F44B20AEB21814A2B62D985EC96A6CAEAC3932BE67E7B44340AD996977B0E255C
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 85 ab 04 a8 c4 d5 51 90-d0 e2 be 05 46 07 67 95   ......Q.....F.g.
    0010 - fa 48 33 5f a2 b8 37 bf-76 80 d4 69 57 90 c8 ab   .H3_..7.v..iW...
    0020 - 60 69 ec 06 61 e8 91 8e-08 dd 33 ad b6 e8 29 93   `i..a.....3...).
    0030 - 7d a3 05 1c fa e6 dd 9c-38 d9 1a 99 ce 0c 7e 76   }.......8.....~v
    0040 - ff 9a dc d1 1b ef 09 45-26 24 20 56 e5 84 0f 63   .......E&$ V...c
    0050 - c9 04 52 0e 92 a3 f2 7c-d6 dd 19 fb f0 61 35 0e   ..R....|.....a5.
    0060 - b8 2c 29 45 f0 af 28 91-e5 43 ea 2c 01 0b 8c 63   .,)E..(..C.,...c
    0070 - d0 39 86 28 80 e8 1f f6-ab fb 33 8d 32 b4 2e 32   .9.(......3.2..2
    0080 - 67 1e ef 3f ec 47 15 94-a5 48 16 1c 3b 82 a1 e5   g..?.G...H..;...
    0090 - 92 88 26 88 b8 50 46 43-88 28 f3 17 ec 11 be 95   ..&..PFC.(......
    00a0 - 63 78 eb 74 aa 36 64 62-1c 78 6a 6c 7f 92 7d 37   cx.t.6db.xjl..}7
    00b0 - 45 d4 15 90 82 42 99 98-20 6b 1b be f9 80 fa 7d   E....B.. k.....}
    00c0 - c1 09 35 9e eb 1e 4d 8f-8e b1 ea dd da ec da 24   ..5...M........$

    Start Time: 1662646824
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
    Session-ID: D377CE70D22B72233499AB687C1AC8B2DFEBBB4E2DC7304831083D639D46EE28
    Session-ID-ctx: 
    Resumption PSK: ACF345DEB5EE15A42EF95A9CAD4C1EF14F93081D9CC34E47F6ED8768AABFB9939A89DFA934C7CCD03466D43C63147B7B
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 85 ab 04 a8 c4 d5 51 90-d0 e2 be 05 46 07 67 95   ......Q.....F.g.
    0010 - 07 2b 40 cd aa 08 fd c4-c6 61 e4 3b a3 b0 81 11   .+@......a.;....
    0020 - 0f 68 9d 99 5e 44 07 cc-12 87 45 4c a0 63 7a f5   .h..^D....EL.cz.
    0030 - d6 55 54 69 c4 e0 be ae-4e 55 cf 7b 7a 93 e2 ce   .UTi....NU.{z...
    0040 - c1 7d b9 65 ab 26 44 f2-ff 70 dc 51 60 ef 93 4e   .}.e.&D..p.Q`..N
    0050 - 3e 40 bc bf 63 0e 31 dc-98 82 17 20 8f 34 f5 f8   >@..c.1.... .4..
    0060 - a7 9e 75 57 a8 40 0d 6d-b9 3c eb 44 a9 a4 3b e4   ..uW.@.m.<.D..;.
    0070 - a8 5c 7a a3 0a 7f 3b 53-3f 47 9b f3 bf f6 71 1c   .\z...;S?G....q.
    0080 - 31 09 55 d5 4a 7c 03 d4-3e 18 1d 23 41 aa 07 07   1.U.J|..>..#A...
    0090 - 34 12 4d 9a de f7 95 27-6f db 30 60 b7 91 99 4f   4.M....'o.0`...O
    00a0 - 2a b8 92 ca 12 c0 f8 85-ed f7 3b c0 6c 1f 90 03   *.........;.l...
    00b0 - 61 3c 17 69 27 41 75 8a-1e 16 a0 1b 97 c4 12 4a   a<.i'Au........J
    00c0 - 1c fe 1a 17 11 33 8e e9-7d 4e ab cf 80 5e 6b 3e   .....3..}N...^k>

    Start Time: 1662646824
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$ 

```

## Notas adicionales

## Referencias
[Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Secure_Socket_Layer)
[OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)
