# Power Cookie
# Descripción
Can you get the flag? Go to this [website](http://saturn.picoctf.net:64169/) and see what you can discover.
# Solución
picoCTF{gr4d3_A_c00k13_65fd1e1a}
En este reto inspeccioné las cookies utilizadas por la página web mediante las herramientas de desarrollador del navegador. Identifiqué una cookie que controlaba los privilegios del usuario y modifiqué manualmente su valor para simular acceso de administrador. Al recargar la página, la aplicación aceptó la cookie modificada y mostró la bandera.
# Notas
# Referencias
