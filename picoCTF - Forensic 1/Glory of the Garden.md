# Glory of the Garden
# Descripción
This file contains more than it seems. Get the flag from [garden.jpg](https://challenge-files.picoctf.net/c_fickle_tempest/39ad2588c3c0db341eff579d7cf894efc34a3b8174368eee2ea0e5ea06516238/garden.jpg).

# Solución
picoCTF{more_than_m33ts_the_3y339cbe6dc}

En este reto descargué la imagen `garden.jpg` y analicé su contenido usando la herramienta `strings`, que permite extraer texto legible de archivos binarios. Al buscar la cadena `pico`, encontré la bandera incrustada dentro del archivo de imagen.

```
┌──(erasmo㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/39ad2588c3c0db341eff579d7cf894efc34a3b8174368eee2ea0e5ea06516238/garden.jpg
--2026-03-12 19:45:59--  https://challenge-files.picoctf.net/c_fickle_tempest/39ad2588c3c0db341eff579d7cf894efc34a3b8174368eee2ea0e5ea06516238/garden.jpg
Resolviendo challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.84, 3.161.44.22, 3.161.44.61, ...
Conectando con challenge-files.picoctf.net (challenge-files.picoctf.net)[3.161.44.84]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 2295191 (2.2M) [application/octet-stream]
Grabando a: «garden.jpg»

garden.jpg          100%[================>]   2.19M   185KB/s    en 19s     

2026-03-12 19:46:20 (121 KB/s) - «garden.jpg» guardado [2295191/2295191]

                                                                             
┌──(erasmo㉿kali)-[~]
└─$ strings garden.jpg | grep pico
Here is a flag: picoCTF{more_than_m33ts_the_3y339cbe6dc}
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ 

```
# Notas
# Referencias
