Suppose users Alice and Bob enter into a key agreement with p = 101 and g = 17. Suppose. Alice chooses x = 19 and Bob chooses y = 13. Determine the key they will share.

## Solución
``` python
>>> p=101
>>> g = 17
>>> x = 19
>>> y = 13
>>> bob = pow(g,x) % p
>>> alice = pow(g,y) % p
>>> flag = pow(g,(x*y)) % p
>>> print(flag)
14
>>> 

```