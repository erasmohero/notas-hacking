# PW Crack 1
# Descripción
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.
# Solución
picoCTF{545h_r1ng1ng_56891419}

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

erasmo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.py
--2026-02-24 04:16:46--  https://artifacts.picoctf.net/c/10/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.18, 3.170.131.33, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py           100%[==================>]     876  --.-KB/s    in 0s      

2026-02-24 04:16:47 (16.4 MB/s) - 'level1.py' saved [876/876]

erasmo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
--2026-02-24 04:17:31--  https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.33, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc 100%[==================>]      30  --.-KB/s    in 0s      

2026-02-24 04:17:31 (1.21 MB/s) - 'level1.flag.txt.enc' saved [30/30]

erasmo-picoctf@webshell:~$ python3 pw_crack_1.py
python3: can't open file '/home/erasmo-picoctf/pw_crack_1.py': [Errno 2] No such file or directory
erasmo-picoctf@webshell:~$ ls
README.txt  codebook.txt  echo       fixme2.py   level1.flag.txt.enc  runme.py
code.py     convertme.py  fixme1.py  glitch.txt  level1.py
erasmo-picoctf@webshell:~$ python3 level1.py
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
erasmo-picoctf@webshell:~$ 
```


# Notas
# Referencias
