#  So Meta
# Descripción
Find the flag in this [picture](https://challenge-files.picoctf.net/c_fickle_tempest/5efde1f80766d292b7da31469bd46cc06ea5bfa456b2013343e20b64a59e7edc/pico_img.png).
# Solución
picoCTF{s0_m3ta_b309a657}

En este reto analicé los metadatos del archivo `pico_img.png`. Utilicé la herramienta `exiftool` para inspeccionar la información almacenada en la imagen. Dentro de la metadata encontré la bandera almacenada en uno de los campos del archivo.

```
┌──(erasmo㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/5efde1f80766d292b7da31469bd46cc06ea5bfa456b2013343e20b64a59e7edc/pico_img.png
--2026-03-12 19:50:35--  https://challenge-files.picoctf.net/c_fickle_tempest/5efde1f80766d292b7da31469bd46cc06ea5bfa456b2013343e20b64a59e7edc/pico_img.png
Resolviendo challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.103, 3.161.44.61, 3.161.44.22, ...
Conectando con challenge-files.picoctf.net (challenge-files.picoctf.net)[3.161.44.103]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 108795 (106K) [application/octet-stream]
Grabando a: «pico_img.png»

pico_img.png        100%[================>] 106.25K   145KB/s    en 0.7s    

2026-03-12 19:50:38 (145 KB/s) - «pico_img.png» guardado [108795/108795]

                                                                             
┌──(erasmo㉿kali)-[~]
└─$ exiftool pico_img.png
ExifTool Version Number         : 13.36
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2025:11:21 13:10:59-06:00
File Access Date/Time           : 2026:03:12 19:50:38-06:00
File Inode Change Date/Time     : 2026:03:12 19:50:38-06:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : picoCTF{s0_m3ta_b309a657}
Image Size                      : 600x600
Megapixels                      : 0.360
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ 

```
# Notas
# Referencias
