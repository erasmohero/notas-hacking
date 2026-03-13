# What Lies Within

# Descripción
There's something in the [building](https://challenge-files.picoctf.net/c_fickle_tempest/c0eec6af0f04316e2bdc4a9f095afd0e2d0121f5e543dbc4a65bb0038d72a993/buildings.png). Can you retrieve the flag?
# Solución
picoCTF{h1d1ng_1n_th3_b1t5}
```
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/c0eec6af0f04316e2bdc4a9f095afd0e2d0121f5e543dbc4a65bb0038d72a993/buildings.png
--2026-03-12 20:41:02--  https://challenge-files.picoctf.net/c_fickle_tempest/c0eec6af0f04316e2bdc4a9f095afd0e2d0121f5e543dbc4a65bb0038d72a993/buildings.png
Resolviendo challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.103, 3.161.44.61, ...
Conectando con challenge-files.picoctf.net (challenge-files.picoctf.net)[3.161.44.22]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 625219 (611K) [application/octet-stream]
Grabando a: «buildings.png»

buildings.png       100%[================>] 610.57K  75.3KB/s    en 8.1s    

2026-03-12 20:41:11 (75.3 KB/s) - «buildings.png» guardado [625219/625219]

                                                                             
┌──(erasmo㉿kali)-[~]
└─$ sudo apt install ruby
gem install zsteg
[sudo] contraseña para erasmo: 
ruby ya está en su versión más reciente (1:3.3+b1).
fijado ruby como instalado manualmente.
Resumen:                        
  Actualizando: 0, Instalando 0, Eliminando: 0, no actualizando: 1632
Fetching zsteg-0.2.14.gem
Fetching rainbow-3.1.1.gem
Fetching iostruct-0.7.0.gem
Fetching zpng-0.4.6.gem
Defaulting to user installation because default installation directory (/var/lib/gems/3.3.0) is not writable.
Successfully installed rainbow-3.1.1
Defaulting to user installation because default installation directory (/var/lib/gems/3.3.0) is not writable.
Successfully installed iostruct-0.7.0
Defaulting to user installation because default installation directory (/var/lib/gems/3.3.0) is not writable.
WARNING:  You don't have /home/erasmo/.local/share/gem/ruby/3.3.0/bin in your PATH,
          gem executables (zpng) will not run.
Successfully installed zpng-0.4.6
Defaulting to user installation because default installation directory (/var/lib/gems/3.3.0) is not writable.
WARNING:  You don't have /home/erasmo/.local/share/gem/ruby/3.3.0/bin in your PATH,
          gem executables (zsteg, zsteg-mask, zsteg-reflow) will not run.
Successfully installed zsteg-0.2.14
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for iostruct-0.7.0
Installing ri documentation for iostruct-0.7.0
Parsing documentation for zpng-0.4.6
Installing ri documentation for zpng-0.4.6
Parsing documentation for zsteg-0.2.14
Installing ri documentation for zsteg-0.2.14
Done installing documentation for rainbow, iostruct, zpng, zsteg after 0 seconds
4 gems installed
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ zsteg buildings.png
zsteg: no se encontró la orden
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ sudo gem install zsteg
Fetching zsteg-0.2.14.gem
Fetching rainbow-3.1.1.gem
Fetching iostruct-0.7.0.gem
Fetching zpng-0.4.6.gem
Successfully installed rainbow-3.1.1
Successfully installed iostruct-0.7.0
Successfully installed zpng-0.4.6
Successfully installed zsteg-0.2.14
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for iostruct-0.7.0
Installing ri documentation for iostruct-0.7.0
Parsing documentation for zpng-0.4.6
Installing ri documentation for zpng-0.4.6
Parsing documentation for zsteg-0.2.14
Installing ri documentation for zsteg-0.2.14
Done installing documentation for rainbow, iostruct, zpng, zsteg after 0 seconds
4 gems installed
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ zsteg buildings.png   
b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
b1,abgr,msb,xy      .. file: OpenPGP Secret Key
b2,b,lsb,xy         .. text: "XuH}p#8Iy="
b3,abgr,msb,xy      .. text: "t@Wp-_tH_v\r"
b4,r,lsb,xy         .. text: "fdD\"\"\"\" "
b4,r,msb,xy         .. text: "%Q#gpSv0c05"
b4,g,lsb,xy         .. text: "fDfffDD\"\""
b4,g,msb,xy         .. text: "f\"fff\"\"DD"
b4,b,lsb,xy         .. text: "\"$BDDDDf"
b4,b,msb,xy         .. text: "wwBDDDfUU53w"
b4,rgb,msb,xy       .. text: "dUcv%F#A`"
b4,bgr,msb,xy       .. text: " V\"c7Ga4"
b4,abgr,msb,xy      .. text: "gOC_$_@o"
                                                                             
┌──(erasmo㉿kali)-[~]
└─$ 

```
En este reto analicé la imagen `buildings.png` buscando datos ocultos. Utilicé la herramienta `zsteg` para examinar los bits menos significativos (LSB) de la imagen, donde encontré una cadena codificada en Base64. Al decodificarla obtuve la bandera.
# Notas
# Referencias
