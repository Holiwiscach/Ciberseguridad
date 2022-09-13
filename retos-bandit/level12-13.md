# Level 12-13
## Objetivo
La clave para el siguiente nivel esta almacenado en **data.txt**, donde es un archivo hexadecimal comprimido. Puede ser util crear un directorio bajo /tmp en el que pueda trabajar usando mkdir. Por ejemplo: mkdir/tmp/myname123. Luego copie el archivo de datos cp, y cambie el nombre de mv

## Datos de acceso
bandit.labs.overthewire.org
bandit13
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## Solución
``` bash
bandit12@bandit:~$ xxd -r data.txt 
i���hta2.bin?��BZh91AY&SY]��������������Ͼ�~�9?����Ͽ>�����; P4�4��
����4��hz@4@�4h��h4����ht�#@����������4@
       M����(�`�*�5jk=\�
8��!Ko�9��%n���k�g3�z]!����w_D0��0�y(���S0q�Y��@u�<[�J�4�C۞sV�==��k�G�Ls��$W1� cE���.��c�L�A
2��|ꂠ�N���u6,r�Hz��0�,YS�Z!N�j3�a B�dq�B��;n�^~���s.�P	�����D���{���������g<�

                                                                              �@Hi}�����`pɬPʭ���"o�u����$�H�$�q���JHH���d{O;�;��$��H��������@�oZ��Tx�C�!��V<�a+nbandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat| bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:~$ 

```

## Notas adicionales

## Referencias
[Hex dump on wikipedia](https://en.wikipedia.org/wiki/Hex_dump)
