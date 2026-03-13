# m00nwalk
# Descripción
Decode this [message](https://challenge-files.picoctf.net/c_fickle_tempest/67884a117da864fd93ca3cfc5d8b4d1aae71c84d7f3d2a89c1b5d0b3a19e0a71/message.wav) from the moon.
# Solución
picoCTF{beep_boop_im_in_space}

sstv -d message.wav -o flag.png y abrimos la imagen 
En este reto utilicé un decodificador SSTV dentro de un entorno virtual de Python para evitar conflictos con la instalación del sistema. Después descargué el archivo `message.wav` y lo convertí en una imagen. Al reconstruir la imagen transmitida en el audio, fue posible observar la bandera.
# Notas
# Referencias
