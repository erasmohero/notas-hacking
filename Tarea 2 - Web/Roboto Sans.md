# Roboto Sans
# Descripción
The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:64249/) out.

# Solución
picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
En este reto revisé el archivo `robots.txt` del sitio web y encontré varias cadenas aparentemente ocultas. Una de ellas estaba codificada en Base64. Al decodificarla obtuve la ruta `js/myfile.txt`. Al acceder a ese archivo dentro del servidor encontré la bandera.
# Notas
# Referencias
