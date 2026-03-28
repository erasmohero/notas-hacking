# Hidden Cipher 1
# Descripción
The flag is right in front of you; just slightly encrypted. All you have to do is figure out the cipher and the key. You can download the program files here. Connect to the program with netcat: nc candy-mountain.picoctf.net 62946
# Solución
picoCTF{xor_unpack_4nalys1s_94993eed}

```
Resolución – Hidden Cipher 1
1. Conexión al servicio

Primero me conecté con nc para ver qué entregaba el reto:

nc candy-mountain.picoctf.net 62946

El servidor devolvió este texto cifrado en hexadecimal:

235a201d702015483b1d412b265d3313501f0c072d135f0d2002302d0a406a0a701756102e
2. Identificación del tipo de cifrado

La pista del reto decía:

Think XOR. What happens when you XOR something twice with the same key?

Eso sugiere que el mensaje fue cifrado con XOR, y que para recuperarlo basta con volver a aplicar XOR usando la misma clave.

Además, como las flags de picoCTF casi siempre empiezan con:

picoCTF{

se puede hacer un known-plaintext attack, usando ese prefijo conocido para recuperar parte de la clave.

3. Recuperación de la clave

Tomé los primeros bytes del cifrado y les apliqué XOR con picoCTF{:

cipher = bytes.fromhex("235a201d702015483b1d412b265d3313501f0c072d135f0d2002302d0a406a0a701756102e")
known  = b"picoCTF{"

partial_key = bytes([cipher[i] ^ known[i] for i in range(len(known))])
print(partial_key)

El resultado fue:

b'S3Cr3tS3'

Eso ya dejaba ver un patrón claro: la clave parecía ser una palabra repetida.

4. Determinación de la longitud real de la clave

Probando el patrón, se observó que la clave mínima coherente era:

S3Cr3t

y que el resto era solo repetición de esa misma cadena.

Por lo tanto, la clave usada en el XOR era:

S3Cr3t
5. Descifrado del mensaje completo

Con la clave ya identificada, apliqué XOR a todo el ciphertext:

cipher = bytes.fromhex("235a201d702015483b1d412b265d3313501f0c072d135f0d2002302d0a406a0a701756102e")
key = b"S3Cr3t"

flag = bytes([b ^ key[i % len(key)] for i, b in enumerate(cipher)])
print(flag.decode())
6. Resultado

La salida fue:

picoCTF{xor_unpack_4nalys1s_94993eed}

```
# Notas
# Referencias
