Can you reverse this [Windows Binary](https://jupiter.challenges.picoctf.org/static/0ef5d0d6d552cd5e0bd60c2adbddaa94/win-exec-1.exe)?

Hints:
1. Microsoft provides windows virtual machines https://developer.microsoft.com/en-us/windows/downloads/virtual-machines
2. Ollydbg may be helpful
3. Flag format: PICOCTF{XXXX}

## Solución

``` bash
sudo dpkg --add-architecture i386
sudo apt install wine
sudo apt install wine32:i386

```

``` bash

```
