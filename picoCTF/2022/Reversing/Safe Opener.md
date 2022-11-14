Can you open this safe? I forgot the key to my safe but this [program](https://artifacts.picoctf.net/c/463/SafeOpener.java) is supposed to help me with retrieving the lost key. Can you help me unlock my safe? Put the password you recover into the picoCTF flag format like: `picoCTF{password}`

## Solución

Al ejecutar el código, nos pide que le demos un password, al darselo no lo encripta en base64 y nos da un mensaje de que el password es incorrecto, es aquí en dónde entramos al código.

Estando en el código, podemos observar que hay un método **openSafe**.
``` java
public static boolean openSafe(String password) {

String encodedkey = "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz";

if (password.equals(encodedkey)) {

System.out.println("Sesame open");

return true;

}

else {

System.out.println("Password is incorrect\n");

return false;

}

}
```

El cual contiene una cadena encriptada y que es comparada con el password dado desde el teclado. Entonces lo que se hace es tomar cadena de caracteres y desencriptarla con base 64.

bandera:
picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}