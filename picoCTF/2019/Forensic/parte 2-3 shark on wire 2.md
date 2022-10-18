We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

Hints:

## Solución
Usamos wireshark para analizar
Al estar analizando los paquetes, encontramos un mensaje dentro de un UDP stream, especifico en el 32, nos muestra el mensaje **start** y en el 60 tambien encontramos uno que llama la atencion, nos muestra **end**, lo curioso es que los dos inician en el puerto 5000 y van al 22, podemos filtrarlos 
donde nos aparece **udp.stream eq 60** escribimos **udp.dstport == 22** que es lo que nos interesa por ahora
Entonces vemos que nos queda una serie de paquetes, y si nos fijamos en el puerto de origen vemos que todos estan dentro del rango de 5000, si a el numero de puerto le restamos 5000, y el valor restante lo transformamos segun su valor ASCII podemos sacar la bandera
Automatizaremos el proceso con un exploit en pyhton

``` python
from scapy.all import *

packets = rdpcap('capture(1).pcap')
flag=''
for p in packets:
      if UDP in p and p[UDP].dport == 22:
         if p[UDP].sport > 5000: 
            flag += chr (p[UDP].sport - 5000)

print(flag)

```

bandera:
picoCTF{p1LLf3r3d_data_v1a_st3g0}
