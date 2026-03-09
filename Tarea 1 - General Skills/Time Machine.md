# Time Machine
# Descripción
What was I last working on? I remember writing a note to help me remember... You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/160/challenge.zip)
# Solución

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

erasmo-picoctf@webshell:~$ wget -q unzip https://artifacts.picoctf.net/c_titan/160/challenge.zip
erasmo-picoctf@webshell:~$ ls
README.txt       codebook.txt  fixme2.py            level2.py
challenge.zip    convertme.py  glitch.txt           level3.flag.txt.enc
challenge.zip.1  drop-in       level1.flag.txt.enc  level3.hash.bin
challenge.zip.2  echo          level1.py            level3.py
code.py          fixme1.py     level2.flag.txt.enc  runme.py
erasmo-picoctf@webshell:~$ unzip challenge.zip.2 
Archive:  challenge.zip.2
replace drop-in/message.txt? [y]es, [n]o, [A]ll, [N]one, [r]ename: A
  inflating: drop-in/message.txt     
  inflating: drop-in/.git/description  
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
  inflating: drop-in/.git/info/exclude  
 extracting: drop-in/.git/refs/heads/master  
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/89/
 extracting: drop-in/.git/objects/89/d296ef533525a1378529be66b22d6a2c01e530  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
  inflating: drop-in/.git/logs/HEAD  
  inflating: drop-in/.git/logs/refs/heads/master  
erasmo-picoctf@webshell:~$ cd drop-in/
erasmo-picoctf@webshell:~/drop-in$ ls
message.txt
erasmo-picoctf@webshell:~/drop-in$ cat message.txt
This is what I was working on, but I'd need to look at my commit history to know why...erasmo-picoctf@webshell:~/drop-in$ git log


erasmo-picoctf@webshell:~/drop-in$ 
```

```
commit 89d296ef533525a1378529be66b22d6a2c01e530 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:22 2024 +0000

    picoCTF{t1m3m@ch1n3_186cd7d7}
(END)
```
# Notas
# Referencias
