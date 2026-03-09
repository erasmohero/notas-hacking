# Binary Search
# Descripción
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses. Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools! You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/4/challenge.zip)

`ssh -p 57770 ctf-player@atlas.picoctf.net` Using the password `83dcefb7`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
# Solución
picoCTF{g00d_gu355_ee8225d0}

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

erasmo-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c_atlas/19/challenge.zip
erasmo-picoctf@webshell:~$ ls
README.txt       challenge.zip.5  echo                 level2.flag.txt.enc
challenge.zip    challenge.zip.6  fixme1.py            level2.py
challenge.zip.1  code.py          fixme2.py            level3.flag.txt.enc
challenge.zip.2  codebook.txt     glitch.txt           level3.hash.bin
challenge.zip.3  convertme.py     level1.flag.txt.enc  level3.py
challenge.zip.4  drop-in          level1.py            runme.py
erasmo-picoctf@webshell:~$ unzip challenge.zip.6
Archive:  challenge.zip.6
   creating: home/ctf-player/drop-in/
  inflating: home/ctf-player/drop-in/guessing_game.sh  
erasmo-picoctf@webshell:~$ ls
README.txt       challenge.zip.6  fixme2.py            level3.flag.txt.enc
challenge.zip    code.py          glitch.txt           level3.hash.bin
challenge.zip.1  codebook.txt     home                 level3.py
challenge.zip.2  convertme.py     level1.flag.txt.enc  runme.py
challenge.zip.3  drop-in          level1.py
challenge.zip.4  echo             level2.flag.txt.enc
challenge.zip.5  fixme1.py        level2.py
erasmo-picoctf@webshell:~$ ssh -p 57770 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:57770 ([18.217.83.136]:57770)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:57770' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Lower! Try again.
Enter your guess: 125
Lower! Try again.
Enter your guess: 62
Lower! Try again.
Enter your guess: 31
Higher! Try again.
Enter your guess: 46
Higher! Try again.
Enter your guess: 54
Congratulations! You guessed the correct number: 54
Here's your flag: picoCTF{g00d_gu355_ee8225d0}
Connection to atlas.picoctf.net closed.
erasmo-picoctf@webshell:~$ 
```

# Notas
# Referencias
