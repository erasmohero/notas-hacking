# Gatekeeper
# Descripción
What’s behind the numeric gate? You only get access if you enter the right kind of number. You can download the program file here. Reverse the program behavior and find what input grants access to the secret flag. nc green-hill.picoctf.net 62861.
# Solución
picoCTF{3_digit_hex_GT_999_b639d748}
```

Primero analicé el binario con nm y objdump, donde identifiqué las funciones is_valid_decimal, is_valid_hex y reveal_flag. Eso permitió inferir que el programa aceptaba entradas decimales o hexadecimales y luego comparaba su valor numérico.

En main observé tres condiciones clave: el valor debía ser mayor que 999, menor o igual que 9999, y además la longitud del input debía ser exactamente 3 caracteres. Esa combinación es imposible para decimal puro, así que concluí que la entrada correcta debía ser hexadecimal de 3 caracteres.

Probé con 3e8, ya que es un hexadecimal válido de longitud 3 y equivale a 1000 en decimal, cumpliendo > 999. Al enviarlo al servicio remoto, el programa concedió acceso y mostró una cadena ofuscada.

La cadena resultante estaba separada por el patrón ftc_oc_ip. Separé los fragmentos, invertí el orden de los bloques y luego invertí cada bloque individualmente. Con eso recuperé la flag final:

picoCTF{3_digit_hex_GT_999_b639d748}


```
# Notas
# Referencias
