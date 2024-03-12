## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.
## Pistas
Try using a tool like Wireshark

What are streams?
## Solucion
```
──(hectorr㉿kali2024)-[~/picoCTF/Forensic/sharkomwire1]
└─$ wireshark capture.pcap

picoCTF{StaT31355_636f6e6e}
```
## Notas adicionales 
utilizamos el uso de wireshark mas el archivo y nos arrojo una conexiones y paquetes del archivo 
le damos click derecho a **UDP**  y nos vamos a **follow** y **stream** por que udp es el que arroja conexiones. y buscamos cual tiene la bandera en todos los upd y listo
## Referencias 