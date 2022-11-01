Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/eb5e6df8e14c52873cf88c582a1a4008/ciphertext)? Something seems a bit small.

Hints:
1. RSA [tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
2. How could having too small an e affect the security of this 2048 bit key?
3. Make sure you don't lose precision, the numbers are pretty big (besides the e value)

## Solución

``` bash
sudo apt install libmpc-dev

python3 -m pip install gmpy2
python3 -m pip install pycryptodome
```


### Algoritmos
- Asimetricos
	- Llave publica - Todos
	- Llave privada - Se mantiene privada
- Simetricos
	- Llave

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