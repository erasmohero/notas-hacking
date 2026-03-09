# Collaborative Development
# Descripción
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/179/challenge.zip)
# Solución
```
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_798f9981}
```

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

erasmo-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/179/challenge.zip
--2026-03-08 23:46:53--  https://artifacts.picoctf.net/c_titan/179/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.72, 3.170.131.77, 3.170.131.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.72|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24648 (24K) [application/octet-stream]
Saving to: 'challenge.zip.5'

challenge.zip.5     100%[==================>]  24.07K  --.-KB/s    in 0.01s   

2026-03-08 23:46:53 (2.26 MB/s) - 'challenge.zip.5' saved [24648/24648]

erasmo-picoctf@webshell:~$ ls
README.txt       challenge.zip.5  fixme1.py            level2.py
challenge.zip    code.py          fixme2.py            level3.flag.txt.enc
challenge.zip.1  codebook.txt     glitch.txt           level3.hash.bin
challenge.zip.2  convertme.py     level1.flag.txt.enc  level3.py
challenge.zip.3  drop-in          level1.py            runme.py
challenge.zip.4  echo             level2.flag.txt.enc
erasmo-picoctf@webshell:~$ unzip challenge.zip.5
Archive:  challenge.zip.5
replace drop-in/.git/description? [y]es, [n]o, [A]ll, [N]one, [r]ename: A    
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
  inflating: drop-in/.git/refs/heads/main  
   creating: drop-in/.git/refs/heads/feature/
 extracting: drop-in/.git/refs/heads/feature/part-1  
 extracting: drop-in/.git/refs/heads/feature/part-2  
 extracting: drop-in/.git/refs/heads/feature/part-3  
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
 extracting: drop-in/.git/objects/77/d6ceca6fe23b57d88cf16f20003e10d6715690  
 extracting: drop-in/.git/objects/b9/32e8c048154a46d224cd7691c99dc8cb88164a  
 extracting: drop-in/.git/objects/5e/4b2dae1868abb644627483c78a683286dfe67c  
 extracting: drop-in/.git/objects/6e/17fb3a35364b4f9bb8bef8b5e6a5af2d3e7dfa  
 extracting: drop-in/.git/objects/43/e44dd37ba0c0adc3d78d0b85d699859ec8d75c  
 extracting: drop-in/.git/objects/30/0cff1bf1f64637dd9ff603d90176e8e8bdeb01  
 extracting: drop-in/.git/objects/7a/b4e25c0cd108374b2275fdb1fcdf635e591833  
 extracting: drop-in/.git/objects/d1/f3407cee4479c075997b497fa290ca636fe258  
   creating: drop-in/.git/objects/74/
 extracting: drop-in/.git/objects/74/989a4f650d024929388b6788d2b4c214a07e49  
 extracting: drop-in/.git/objects/c3/1215218d31567374eeed51505972af2ed46a37  
   creating: drop-in/.git/objects/04/
 extracting: drop-in/.git/objects/04/ebe96db2885e1a7af6d1e4ca7ce9b89e5ba743  
 extracting: drop-in/.git/objects/12/c2ae89d8035b7a5aa7cd169dc9e93cc68201be  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
  inflating: drop-in/.git/logs/HEAD  
  inflating: drop-in/.git/logs/refs/heads/main  
   creating: drop-in/.git/logs/refs/heads/feature/
  inflating: drop-in/.git/logs/refs/heads/feature/part-1  
  inflating: drop-in/.git/logs/refs/heads/feature/part-2  
  inflating: drop-in/.git/logs/refs/heads/feature/part-3  
  inflating: drop-in/flag.py         
erasmo-picoctf@webshell:~$ cd drop-in/
erasmo-picoctf@webshell:~/drop-in$ ls
flag.py  message.py  message.txt
erasmo-picoctf@webshell:~/drop-in$ git branch -a

[1]+  Stopped                 git branch -a
erasmo-picoctf@webshell:~/drop-in$ git show feature/part-1

[2]+  Stopped                 git show feature/part-1
erasmo-picoctf@webshell:~/drop-in$ git show feature/part-2

[3]+  Stopped                 git show feature/part-2
erasmo-picoctf@webshell:~/drop-in$ git show feature/part-3

[4]+  Stopped                 git show feature/part-3
erasmo-picoctf@webshell:~/drop-in$ 
```


```
commit 300cff1bf1f64637dd9ff603d90176e8e8bdeb01 (feature/part-1)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    add part 1

diff --git a/flag.py b/flag.py
index 77d6cec..6e17fb3 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,2 @@
 print("Printing the flag...")
+print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file
(END)
```

```
commit 74989a4f650d024929388b6788d2b4c214a07e49 (feature/part-2)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    add part 2

diff --git a/flag.py b/flag.py
index 77d6cec..7ab4e25 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("m@k3s_th3_dr3@m_", end='')
\ No newline at end of file
(END)
```

```
commit 12c2ae89d8035b7a5aa7cd169dc9e93cc68201be (feature/part-3)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    add part 3

diff --git a/flag.py b/flag.py
index 77d6cec..c312152 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("w0rk_798f9981}")
(END)
```
# Notas
# Referencias
