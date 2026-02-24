# runme.py
# Descripción
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell. [Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

# Solución
picoCTF{run_s4n1ty_run}

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

erasmo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2026-02-24 03:21:06--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.77, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py            100%[==================>]     270  --.-KB/s    in 0s      

2026-02-24 03:21:06 (154 MB/s) - 'runme.py' saved [270/270]

erasmo-picoctf@webshell:~$ ls
README.txt  echo  glitch.txt  runme.py
erasmo-picoctf@webshell:~$ chmod +x runme.py
erasmo-picoctf@webshell:~$ ./runme.py
picoCTF{run_s4n1ty_run}
erasmo-picoctf@webshell:~$ 
```
# Notas
# Referencias
