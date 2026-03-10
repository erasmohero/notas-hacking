# GET aHEAD
# Descripción
Find the flag being held on this server to get ahead of the competition http://wily-courier.picoctf.net:64123/
# Solución
picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
```
┌──(erasmo㉿kali)-[~]
└─$ curl -I http://wily-courier.picoctf.net:64123/index.php
HTTP/1.1 200 OK
Date: Mon, 09 Mar 2026 22:19:01 GMT
Server: Apache/2.4.38 (Debian)
X-Powered-By: PHP/7.2.34
flag: picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
Content-Type: text/html; charset=UTF-8
```
siguiendo los pasos del video para poder utilizar el post y el head de forma correcta para sacar la bandera
# Notas
# Referencias
https://www.youtube.com/watch?v=oiZk0tIkR48&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=11&pp=iAQB