# Secrets
# Descripción
We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:53812/).
# Solución
picoCTF{succ3ss_@h3n1c@10n_790d2615}
En este reto revisé el código fuente de la página principal y encontré referencias a la carpeta `secret/`. A partir de ahí fui explorando directorios ocultos dentro del sitio hasta llegar a `secret/hidden/superhidden/`. En el código fuente de esa última página encontré la bandera oculta dentro de una etiqueta HTML.

# Notas
# Referencias
