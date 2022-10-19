When a communication protocol is used that does not encrypt the information, it travels in plain text, putting the information at risk. Can you find the flag of this enchilada?

## Solución
Descargado el archivo proporcionado por el reto abrimos con Wireshark, se da click derecho en alguno de TCP, después daremos click en follow > tcp-stream y en stream 37 hay una parte donde dice FLAG.txt, abajo de eso hay algo cifrado en base64, se decifra y obtenemos la bandera.

bandera:
flagMX{Ench1ladaR0jayVerd3}