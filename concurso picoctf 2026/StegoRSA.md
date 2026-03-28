# SUDO MAKE ME A SANDWICH
# Descripción
Can you read the flag? I think you can! `ssh -p 60412 ctf-player@green-hill.picoctf.net` using password `f068c7da`
# Solución
picoCTF{ju57_5ud0_17_2feb37e6}
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

erasmo-picoctf@webshell:~$ ssh -p 60834 ctf-player@green-hill.picoctf.net
The authenticity of host '[green-hill.picoctf.net]:60834 ([3.18.205.4]:60834)' can't be established.
ED25519 key fingerprint is SHA256:6yCIZ8GT1zu0g1/pjVc7t+aLNpxCPniM/MF6w7pTUx0.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[green-hill.picoctf.net]:60834' (ED25519) to the list of known hosts.
ctf-player@green-hill.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.17.0-1007-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ sudo -l
Matching Defaults entries for ctf-player on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User ctf-player may run the following commands on challenge:
    (ALL) NOPASSWD: /bin/emacs
ctf-player@challenge:~$ sudo emacs

[1]+  Stopped                 sudo emacs
ctf-player@challenge:~$ 
```


```
File Edit Options Buffers Tools Complete In/Out Signals Help                   
Welcome to GNU Emacs, one component of the GNU/Linux operating system.

Get help           C-h  (Hold down CTRL and press h)
Emacs manual       C-h r        Browse manuals     C-h i
Emacs tutorial     C-h t        Undo changes       C-x u
Buy manuals        C-h RET      Exit Emacs         C-x C-c
Activate menubar   M-`
(`C-' means use the CTRL key.  `M-' means use the Meta (or Alt) key.
If you have no Meta key, you may instead type ESC followed by the character.)
Useful tasks:
Visit New File                  Open Home Directory
Customize Startup               Open *scratch* buffer

GNU Emacs 26.3 (build 2, x86_64-pc-linux-gnu, GTK+ Version 3.24.14)
 of 2020-03-26, modified by Debian
Copyright (C) 2019 Free Software Foundation, Inc.

GNU Emacs comes with ABSOLUTELY NO WARRANTY; type C-h C-w for full details.
Emacs is Free Software--Free as in Freedom--so you can redistribute copies
of Emacs and modify it; type C-h C-c to see the conditions.
Type C-h C-o for information on getting the latest version.


-=--:%%--F1  *GNU Emacs*    All L2     (Fundamental) --------------------------
root@challenge:/home/ctf-player# cat /root/flag.txt
cat: /root/flag.txt: No such file or directory
root@challenge:/home/ctf-player# find / -name flag.txt 2>/dev/null
/home/ctf-player/flag.txt
root@challenge:/home/ctf-player# cat /home/ctf-player/flag.txt
picoCTF{ju57_5ud0_17_2feb37e6}
root@challenge:/home/ctf-player# 


```
# Notas
# Referencias
