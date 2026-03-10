# Cookies
# Descripción
Who doesn't love cookies? Try to figure out the best one. http://wily-courier.picoctf.net:65531/
# Solución
picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}

se realiza un for para cubrir todas las solicitudes posibles y solo se muestra la que contenga informacion de picoCTF que es la que tiene la bandera 

```
┌──(erasmo㉿kali)-[~]
└─$ for i in {0..20}; do curl -s http://wily-courier.picoctf.net:65531/check -H "Cookie: name=$i"; done | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}
                     
```
# Notas
# Referencias
https://www.youtube.com/watch?v=LseQ-XWCXVo&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=12