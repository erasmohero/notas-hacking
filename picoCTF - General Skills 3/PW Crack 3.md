# PW Crack 3
# Descripción
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

# Solución
picoCTF{m45h_fl1ng1ng_cd6ed2eb}

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

erasmo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.py
--2026-02-24 04:29:00--  https://artifacts.picoctf.net/c/17/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.18, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py           100%[==================>]   1.31K  --.-KB/s    in 0s      

2026-02-24 04:29:00 (487 MB/s) - 'level3.py' saved [1337/1337]

erasmo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
--2026-02-24 04:29:34--  https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.77, 3.170.131.33, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.77|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc 100%[==================>]      31  --.-KB/s    in 0s      

2026-02-24 04:29:35 (1.72 MB/s) - 'level3.flag.txt.enc' saved [31/31]

erasmo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.hash.bin
--2026-02-24 04:29:55--  https://artifacts.picoctf.net/c/17/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.33, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin     100%[==================>]      16  --.-KB/s    in 0s      

2026-02-24 04:29:56 (4.80 MB/s) - 'level3.hash.bin' saved [16/16]

erasmo-picoctf@webshell:~$ 
erasmo-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 87ab                       
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
erasmo-picoctf@webshell:~$ 
```

# Notas
# Referencias
