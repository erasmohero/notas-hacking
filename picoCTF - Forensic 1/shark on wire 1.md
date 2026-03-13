# shark on wire 1
# Descripción
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap). Recover the flag.
# Solución
picoCTF{StaT31355_636f6e6e}
```
┌──(erasmo㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap
--2026-03-12 20:13:42--  https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap
Resolviendo challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.103, 3.161.44.22, 3.161.44.84, ...
Conectando con challenge-files.picoctf.net (challenge-files.picoctf.net)[3.161.44.103]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 239455 (234K) [application/octet-stream]
Grabando a: «capture.pcap»

capture.pcap        100%[================>] 233.84K  79.8KB/s    en 2.9s    

2026-03-12 20:13:46 (79.8 KB/s) - «capture.pcap» guardado [239455/239455]

                                                                             
┌──(erasmo㉿kali)-[~]
└─$ wireshark capture.pcap
```

En este reto analicé el archivo `capture.pcap` utilizando Wireshark. Revisé las conversaciones de red siguiendo los **UDP streams** dentro del tráfico capturado. Al examinar el **stream número 6** se pudo reconstruir la bandera transmitida entre los paquetes.

# Notas
# Referencias
