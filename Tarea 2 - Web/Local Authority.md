# Local Authority
# Descripción
Can you get the flag? Go to this [website](http://saturn.picoctf.net:52385/) and see what you can discover.
# Solución
picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}

En este reto revisé el código fuente de la página web y observé que la validación del usuario y contraseña se realizaba en el lado del cliente mediante el archivo `secure.js`. Al analizar ese script encontré las credenciales correctas dentro de la función `checkPassword`. Utilizando esas credenciales en el formulario de inicio de sesión, la aplicación permitió el acceso y mostró la bandera.
# Notas
# Referencias
