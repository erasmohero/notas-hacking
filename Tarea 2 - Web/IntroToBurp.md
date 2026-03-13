# IntroToBurp
# Descripción
Try [here](http://titan.picoctf.net:61641/) to find the flag
# Solución
picoCTF{#0TP_Bypvss_SuCc3$S_3e3ddc76}

En este reto utilicé Burp Suite para interceptar la petición HTTP enviada durante la verificación del OTP. Antes de reenviar la solicitud eliminé completamente el parámetro `otp` del cuerpo de la petición. Debido a una validación incorrecta en el servidor, la aplicación aceptó la solicitud sin OTP y devolvió la bandera.
# Notas
# Referencias
