# shark on wire 2
# Descripción
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/da02deeb6a0b3cd4fa866b6d1b30190e358240a2cd734c8da5d5a048f87fa038/capture.pcap). Recover the flag.

# Solución
picoCTF{p1LLf3r3d_data_v1a_st3g0}

En este reto analicé el archivo `capture.pcap` con Wireshark y revisé las conversaciones o _streams_ del tráfico capturado. Después de inspeccionar los paquetes relevantes, identifiqué la información exfiltrada dentro del flujo de red y recuperé la bandera.
```
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
    if UDP in p and p[UDP].dport == 22:
        if p[UDP].sport > 5000:
            flag = flag + chr(p[UDP].sport - 5000)

print(flag)
```
python3 exp.py
# Notas
# Referencias
