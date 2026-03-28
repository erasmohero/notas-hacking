# Hidden Cipher 2
# Descripción
The flag is right in front of you... kind of. You just need to solve a basic math problem to see it. But to get the real flag, you’ll have to understand how that math answer is used. You can download the program files here. Connect to the program with netcat: nc crystal-peak.picoctf.net 52026
# Solución
picoCTF{m4th_b3h1nd_c1ph3r_3185ed2e}

```
1. Conexión al servicio

Primero me conecté al reto con nc:

nc crystal-peak.picoctf.net 52026

El programa mostró una operación matemática sencilla:

What is 3 - 2?

Respondí correctamente:

1
2. Observación de la salida

Después de responder bien, el programa devolvió esto:

Encoded flag values:
112, 105, 99, 111, 67, 84, 70, 123, 109, 52, 116, 104, 95, 98, 51, 104, 49, 110, 100, 95, 99, 49, 112, 104, 51, 114, 95, 51, 49, 56, 53, 101, 100, 50, 101, 125

Noté que no era hexadecimal ni base64, sino una secuencia de números decimales.

3. Identificación del formato

Probé interpretar cada valor como un código ASCII decimal.

Por ejemplo:

112 → p

105 → i

99 → c

111 → o

Con eso ya se veía claramente el inicio:

picoCTF{

Así que confirmé que toda la secuencia estaba codificada como caracteres ASCII.

4. Conversión completa

Convertí todos los números a texto. Se puede hacer manualmente o con Python:

vals = [112, 105, 99, 111, 67, 84, 70, 123, 109, 52, 116, 104, 95, 98, 51, 104, 49, 110, 100, 95, 99, 49, 112, 104, 51, 114, 95, 51, 49, 56, 53, 101, 100, 50, 101, 125]
flag = ''.join(chr(x) for x in vals)
print(flag)
5. Resultado

La salida fue:

picoCTF{m4th_b3h1nd_c1ph3r_3185ed2e}

```
# Notas
# Referencias
