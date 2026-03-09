# Special
# Descripción
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM) Start your instance to see connection details. `ssh -p 56461 ctf-player@saturn.picoctf.net` The password is `fd7746b4`
# Solución
picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}
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

erasmo-picoctf@webshell:~$ ssh -p 56461 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:56461 ([13.59.203.175]:56461)' can't be established.
ED25519 key fingerprint is SHA256:tJ0wuU5yBvNO/FrkHmR9iY36VJClMhKV+Hq2sxqKFmg.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:56461' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.8.0-1047-aws x86_64)

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

Special$ */*
*/* 
sh: 1: blargh/flag.txt: Permission denied
Special$ ${parameter=cat < blargh/flag.txt}
${parameter=cat < blargh/flag.txt} 
cat: '<': No such file or directory
picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}Special$ 
```

# Notas
# Referencias
