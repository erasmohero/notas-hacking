# WhitePages
# Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.picoctf.net/c_fickle_tempest/4de4b105d28cb6df34d9805217f2460b978a37dafc3dfc50edadd8d424dd311a/whitepages.txt) is all blank!
# Solución
picoCTF{not_all_spaces_are_created_equal_f5d46aff52c6e17f9fd6317b33d2d783}
En este reto analicé un archivo que aparentemente estaba en blanco. Al revisar su contenido descubrí que utilizaba diferentes tipos de espacios Unicode para ocultar información binaria. Convertí los espacios en bits, agrupé los datos en bytes y los transformé a texto, obteniendo así la bandera.

```
with open("whitepages.txt", "r", encoding="utf-8") as f:
    data = f.read()

# En este reto:
# U+2003 = 0
# espacio normal = 1
bits = data.replace('\u2003', '0').replace(' ', '1')

out = ""
for i in range(0, len(bits), 8):
    byte = bits[i:i+8]
    if len(byte) == 8:
        out += chr(int(byte, 2))

print(out)
```
# Notas
# Referencias
