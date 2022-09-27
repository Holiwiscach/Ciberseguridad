# Based
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

Hints:
- I hear python can convert things.
- It might help to have multiple windows open.

## Solución
``` bash
holiwiscach@ubuntu:~$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
computer
Please give the 01100011 01101111 01101101 01110000 01110101 01110100 01100101 01110010 as a word.
...
you have 45 seconds.....

Input:
computer
Please give me the  160 145 141 162 as a word.
Input:
pear
Please give me the 66616c636f6e as a word.
Input:
falcon
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}

```

[From binary](https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)&input=MDExMDExMDAgMDExMDEwMDEgMDExMDAxMTEgMDExMDEwMDAgMDExMTAxMDA)
[From Octal](https://gchq.github.io/CyberChef/#recipe=From_Octal('Space')&input=MTYzIDE1NCAxNjUgMTQ0IDE0NyAxNDU)
[From Hex](https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=NzQ2MTYyNmM2NQ)