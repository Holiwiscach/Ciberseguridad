We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://artifacts.picoctf.net/c/534/leak.tar). The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.

Hints:
1. Maybe other passwords will have hints about the leak?

## Solución

[CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=Y3ZwYlBHU3tQN2UxU181NEkzNV83MVozfQ)

Creamos un código en python para poder sacar el password.
``` python
n = 0

with open("usernames.txt") as file:
        d = file.readlines()            

        for line in d:
                if (line.replace("\n","") == "cultiris"):
                        break
                n+=1

with open("passwords.txt") as file:           
        d = file.readlines()
        print(d[n])

```

Corremos el python y nos mostrara el pass del usuario.
``` bash
holiwiscach@ubuntu:~/credStuff$ python3 reto.py 
cvpbPGS{P7e1S_54I35_71Z3}

```

Al analizarlo vemos que esta en ROT13, entonces usando la página **CyberChef** podemos decifrar la bandera:

picoCTF{C7r1F_54V35_71M3}