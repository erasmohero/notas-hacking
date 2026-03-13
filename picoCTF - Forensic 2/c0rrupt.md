# c0rrupt
# Descripción
We found this [file](https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery). Recover the flag.
# Solución
picoCTF{c0rrupt10n_1847995}

En este reto analicé el archivo `mystery` con un editor hexadecimal y observé que su cabecera no coincidía con la de un PNG válido. Reemplacé los bytes iniciales por la firma correcta de PNG y después corregí algunos chunks dañados del archivo. Una vez reparada la estructura, el archivo pudo abrirse como imagen y mostró la bandera.
```
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery
xxd -g 1 mystery | head
--2026-03-12 21:44:06--  https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery
Resolviendo challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.84, 3.161.44.61, ...
Conectando con challenge-files.picoctf.net (challenge-files.picoctf.net)[3.161.44.22]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 202940 (198K) [application/octet-stream]
Grabando a: «mystery»

mystery             100%[================>] 198.18K   111KB/s    en 1.8s    

2026-03-12 21:44:10 (111 KB/s) - «mystery» guardado [202940/202940]

00000000: 89 65 4e 34 0d 0a b0 aa 00 00 00 0d 43 22 44 52  .eN4........C"DR
00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
00000040: 00 09 70 48 59 73 aa 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ cp mystery fixed.png
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ printf '\x89\x50\x4E\x47\x0D\x0A\x1A\x0A' | dd of=fixed.png bs=1 seek=0 count=8 conv=notrunc
printf '\x00\x00\x00\x0D\x49\x48\x44\x52' | dd of=fixed.png bs=1 seek=8 count=8 conv=notrunc
8+0 records in
8+0 records out
8 bytes copied, 0.000421754 s, 19.0 kB/s
8+0 records in
8+0 records out
8 bytes copied, 0.00023406 s, 34.2 kB/s
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ cp mystery fixed.png
printf '\x89\x50\x4E\x47\x0D\x0A\x1A\x0A' | dd of=fixed.png bs=1 seek=0 count=8 conv=notrunc
printf '\x00\x00\x00\x0D\x49\x48\x44\x52' | dd of=fixed.png bs=1 seek=8 count=8 conv=notrunc
file fixed.png
xxd -g 1 fixed.png | head
8+0 records in
8+0 records out
8 bytes copied, 0.000404871 s, 19.8 kB/s
8+0 records in
8+0 records out
8 bytes copied, 0.000244924 s, 32.7 kB/s
fixed.png: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
00000000: 89 50 4e 47 0d 0a 1a 0a 00 00 00 0d 49 48 44 52  .PNG........IHDR
00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
00000040: 00 09 70 48 59 73 aa 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ xdg-open fixed.png
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ pngcheck -v fixed.png
No se ha encontrado la orden «pngcheck», pero se puede instalar con:
sudo apt install pngcheck
¿Quiere instalarlo? (N/y)y
sudo apt install pngcheck
[sudo] contraseña para erasmo: 
Instalando:                              
  pngcheck
                                                                             
Resumen:
  Actualizando: 0, Instalando 1, Eliminando: 0, no actualizando: 1632
  Tamaño de la descarga: 70.4 kB
  Espacio necesario: 179 kB / 7 730 MB disponible

Des:1 http://kali.download/kali kali-rolling/main amd64 pngcheck amd64 4.0.1-1 [70.4 kB]
Descargados 70.4 kB en 5s (13.1 kB/s)
Seleccionando el paquete pngcheck previamente no seleccionado.
(Leyendo la base de datos ... 422067 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../pngcheck_4.0.1-1_amd64.deb ...
Desempaquetando pngcheck (4.0.1-1) ...
Configurando pngcheck (4.0.1-1) ...
Procesando disparadores para man-db (2.13.1-1) ...
Procesando disparadores para kali-menu (2025.4.3) ...
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ pngcheck -v fixed.png
File: fixed.png (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in fixed.png
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ xdg-open fixed.png  
```

# Notas
# Referencias
