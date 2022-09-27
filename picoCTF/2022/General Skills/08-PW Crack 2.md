# PW Crack 2
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/16/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level2.flag.txt.enc) in the same directory too.

Hints:
- Does that encoding look familiar?
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
La solución a este problema es entrando al archivo .py, analizando el código verifica si la variable **user_pw** es igual a una cadena especifica **chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)**, viendo esto agrgegamos una linea que nos indique cuál es la contraseña pasada en texto y corriendo el programa usando la linea agregada y mostrada en la terminal como contraseña, permitiendonos obtener la bandera.

``` python
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################

def str_xor(secret, key):

#extend key to secret length

new_key = key

i = 0

while len(new_key) < len(secret):

new_key = new_key + key[i]

i = (i + 1) % len(key)

return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])

###############################################################################

  

flag_enc = open('level2.flag.txt.enc', 'rb').read()

  
  
  

def level_2_pw_check():

print("Password here! " + chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)) ##línea agregada

user_pw = input("Please enter correct password for flag: ")

if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):

print("Welcome back... your flag, user:")

decryption = str_xor(flag_enc.decode(), user_pw)

print(decryption)

return

print("That password is incorrect")

  
  
  

level_2_pw_check()
```

``` bash
holiwiscach@ubuntu:~$ python3 level2.py
Password here! de76
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}

```