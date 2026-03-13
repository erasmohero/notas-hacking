# SQLiLite
# Descripción
Can you login to this website? Try to login [here](http://saturn.picoctf.net:63832/).
# Solución
picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}

En este reto realicé una inyección SQL en el formulario de inicio de sesión utilizando el payload `admin' --`, lo que permitió omitir la verificación de la contraseña. Después de iniciar sesión revisé el código fuente de la página y encontré la bandera oculta en una etiqueta HTML que tenía el atributo `hidden`.
# Notas
# Referencias
