# Shared Secrets
# Descripción
A message was encrypted using a shared secret... but it looks like one side of the exchange leaked something. Can you piece together the secret and get the flag? Download the message. And source code
# Solución
picoCTF{dh_s3cr3t_1b25e19f}

```
1. Análisis inicial

Se descargaron los archivos proporcionados:

message.txt

encryption.py

Se comenzó revisando el contenido del mensaje:

cat message.txt

Se observó una cadena en formato hexadecimal, lo que sugiere que el mensaje fue cifrado y luego codificado.

2. Revisión del código fuente

Se analizó el archivo encryption.py:

cat encryption.py

Se identificó que el cifrado utilizado era una operación XOR entre el mensaje original y una clave (shared secret).

La operación XOR tiene la propiedad:

A XOR B = C
→ entonces C XOR B = A

Esto significa que si conocemos una parte del mensaje original, podemos recuperar la clave.

3. Suposición del formato de la flag

En retos de picoCTF, las flags normalmente comienzan con:

picoCTF{

Por lo tanto, se utilizó este conocimiento como texto conocido (known plaintext).

4. Obtención de la clave

Se convirtieron los primeros bytes del mensaje cifrado de hexadecimal a bytes y se aplicó XOR con "picoCTF{":

enc = bytes.fromhex("839a909cb0a7b588979bac80c09081c087acc291c1c696c2ca958e")
known = b"picoCTF{"

key = enc[0] ^ known[0]
print(hex(key))

El resultado fue:

0xf3

Esto indica que la clave es un solo byte (0xF3) repetido.

5. Descifrado del mensaje completo

Se aplicó XOR a todo el mensaje con la clave obtenida:

enc = bytes.fromhex("839a909cb0a7b588979bac80c09081c087acc291c1c696c2ca958e")
flag = bytes([b ^ 0xF3 for b in enc])
print(flag.decode())
6. Resultado
picoCTF{dh_s3cr3t_1b25e19f}
```
# Notas
# Referencias
