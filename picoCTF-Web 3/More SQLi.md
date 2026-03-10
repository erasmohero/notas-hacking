# More SQLi
# Descripción
Can you find the flag on this website. Try to find the flag [here](http://saturn.picoctf.net:58109/).

# Solución
|     |                                                         |
| --- | ------------------------------------------------------- |
|     | picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_98236ce6} |
se hace una inyeccion basica tomando en cuenta que la pista marca que es en sql lite  en usuario y contraseña se pone ' or 1 == 1;  y se logra entrar y en la seccion de busqueda despues de investigar las tablas y sus contenidos se selecciona la de la bandera con ' union select id,flag,3 from more_table; y sale 
# Notas
# Referencias
https://www.youtube.com/watch?v=clMe4yqL6yU&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=63