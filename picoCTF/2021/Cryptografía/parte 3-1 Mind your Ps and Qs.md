In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values)

Hints:
1. Bits are expensive, I used only a little bit over 100 to save money

## Solución

Descargamos un programa el cuál nos ayuda a factorización de n y la desencriptación de c por lo que solo vamos a ejecutarlo, dar los valores proporcionados por el reto del archivo **values**
``` 
git clone git@github.com:RsaCtfTool/RsaCtfTool.git

sudo pip3 install -r "requirements.txt"
```

Una vez instalado entramos a la carpeta RsaCtfTool y ejecutamos el siguiente comando junto con los valoes de **value**
``` bash
holiwiscach@ubuntu:~/RsaCtfTool$ python3 RsaCtfTool.py -n 1311097532562595991877980619849724606784164430105441327897358800116889057763413423 -e 65537 --uncipher 861270243527190895777142537838333832920579264010533029282104230006461420086153423
private argument is not set, the private key will not be displayed, even if recovered.

...
...

Results for /tmp/tmpe7l7s4zb:

Unciphered data :
HEX : 0x7069636f4354467b736d6131315f4e5f6e305f67306f645f31333638363637397d
INT (big endian) : 13016382529449106065927291425342535437996222135352905256639573959002849415739773
INT (little endian) : 14499890537778393054847079048867328615216804463612385442269942895111379697756528
utf-8 : picoCTF{sma11_N_n0_g0od_13686679}
STR : b'picoCTF{sma11_N_n0_g0od_13686679}'
HEX : 0x007069636f4354467b736d6131315f4e5f6e305f67306f645f31333638363637397d
INT (big endian) : 13016382529449106065927291425342535437996222135352905256639573959002849415739773
INT (little endian) : 3711971977671268622040852236510036125495501942684770673221105381148513202625671168
utf-8 : picoCTF{sma11_N_n0_g0od_13686679}
utf-16 : 瀀捩䍯䙔獻慭ㄱ也湟弰で摯ㅟ㘳㘸㜶紹
STR : b'\x00picoCTF{sma11_N_n0_g0od_13686679}'
```

Bandera:
picoCTF{sma11_N_n0_g0od_13686679}

Notas:

c = texto cifrdo
m = mensaje de texto plan
p = numero primo
q = numero primo
n = modulo
tn = totient n
e = exponente (llave publica) = 65537
d = llave privada

n = p * q
tn = (p-1) * (q-1)
d = e mod inv tn

Encriptar: python pow(m,e,n)
c = m ^ e mod n

Desencriptar: pow(c,d,n)
m = c ^ d mod n