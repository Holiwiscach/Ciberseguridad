Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

Hints:
1. How did pictures from the moon landing get sent back to Earth?
2. What is the CMU mascot?, that might help select a RX option
## Solución
[sstv install](https://github.com/colaclanth/sstv)

``` bash
holiwiscach@ubuntu:~$ cd /opt/
holiwiscach@ubuntu:/opt$ sudo git clone https://github.com/colaclanth/sstv.git
...
holiwiscach@ubuntu:/opt$ cd sstv/
holiwiscach@ubuntu:/opt/sstv$ sudo python3 setup.py install

```

``` bash
holiwiscach@ubuntu:~$ sstv -d message.wav -o messageImg.png

```

bandera:
picoCTF{beep_boop_im_in_space}