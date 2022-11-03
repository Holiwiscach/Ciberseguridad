Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/199/network-dump.flag.pcap)

Hints:
1. Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.

## Solución

Entrando al archivo que nos proporciono el reto, vamos a los protocolos TCP y vamos a seguir el flujo, en el flujo 0 encontramos la bandera.

bandera:
picoCTF{p4ck37_5h4rk_ceccaa7f}