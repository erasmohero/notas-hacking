# extensions
# Descripción
# Solución
picoCTF{now_you_know_about_extensions}
```
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/31fe772e6a4c71e867af0b2a93818e06d8f8ebf8af2a9615495d00356ff576da/flag.txt
--2026-03-12 20:24:53--  https://challenge-files.picoctf.net/c_fickle_tempest/31fe772e6a4c71e867af0b2a93818e06d8f8ebf8af2a9615495d00356ff576da/flag.txt
Resolviendo challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.103, 3.161.44.84, 3.161.44.61, ...
Conectando con challenge-files.picoctf.net (challenge-files.picoctf.net)[3.161.44.103]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 9984 (9.8K) [application/octet-stream]
Grabando a: «flag.txt»

flag.txt            100%[================>]   9.75K  --.-KB/s    en 0s      

2026-03-12 20:24:56 (86.4 MB/s) - «flag.txt» guardado [9984/9984]

                                                                             
┌──(erasmo㉿kali)-[~]
└─$ file flag.txt
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ mv flag.txt flag.png
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ strings flag.png | grep pico
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ xdg-open flag.png
                                                                             
┌──(erasmo㉿kali)-[~]

```

En este reto analicé el archivo `flag.txt` utilizando el comando `file` para identificar su verdadero tipo. Descubrí que el archivo no era texto sino una imagen PNG. Después de cambiar la extensión a `.png` y abrir el archivo, la bandera se encontraba visible dentro de la imagen.
# Notas
# Referencias
