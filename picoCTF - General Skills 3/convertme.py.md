# convertme.py
# Descripción
Run the Python script and convert the given number from decimal to binary to get the flag. [Download Python script](https://artifacts.picoctf.net/c/23/convertme.py)

---

# Solución
picoCTF{4ll_y0ur_b4535_9c3b7d4d}

```

==========================================================================

Welcome to the picoCTF webshell!

💻  The webshell is intended only for solving picoCTF challenges. Any
   other usage is a violation of our terms and conditions.

📹  Sessions are monitored and logged to prevent abuse. Please do not
   enter any sensitive information into the webshell.

🗄  Files stored outside of your home directory will not persist between
   webshell sessions.

🌐  Network connectivity and resources are limited. Some limits can be
   checked by typing usage.

😴  Idle sessions will automatically log out after 15 minutes.

📚  For more information and a beginner's guide, type less ~/README.txt.

==========================================================================

erasmo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/23/convertme.py
--2026-02-24 03:34:40--  https://artifacts.picoctf.net/c/23/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.77, 3.170.131.33, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py        100%[==================>]   1.16K  --.-KB/s    in 0s      

2026-02-24 03:34:41 (440 MB/s) - 'convertme.py' saved [1189/1189]

erasmo-picoctf@webshell:~$ python3 convertme.py
If 73 is in decimal base, what is it in binary base?
Answer: 1000010 
66 and 73 are not equal.
erasmo-picoctf@webshell:~$ python3 convertme.py
If 98 is in decimal base, what is it in binary base?
Answer: 1100010
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}
erasmo-picoctf@webshell:~$ 
```
# Notas
# Referencias
