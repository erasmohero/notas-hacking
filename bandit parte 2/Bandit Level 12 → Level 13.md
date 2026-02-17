# Bandit Level 12 → Level 13
# Descripción
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)
# Solución
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```
C:\Users\ero33>ssh -p 2220 bandit12@bandit.labs.overthewire.org
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit12@bandit.labs.overthewire.org's password:

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$
bandit12@bandit:~$ WORK=$(mktemp -d)
bandit12@bandit:~$ cd "$WORK"
bandit12@bandit:/tmp/tmp.z91sOImHRk$ cp ~/data.txt .
bandit12@bandit:/tmp/tmp.z91sOImHRk$ xxd -r data.txt > blob
bandit12@bandit:/tmp/tmp.z91sOImHRk$ file blob
blob: gzip compressed data, was "data2.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 564
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv blob blob.gz
bandit12@bandit:/tmp/tmp.z91sOImHRk$ gzip -d blob.gz
bandit12@bandit:/tmp/tmp.z91sOImHRk$ file blob
blob: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv blob blob.bz2
bzip2 -d blob.bz2
bandit12@bandit:/tmp/tmp.z91sOImHRk$ file blob
blob: gzip compressed data, was "data4.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv blob blob.gz
gzip -d blob.gz
bandit12@bandit:/tmp/tmp.z91sOImHRk$ file blob
blob: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv blob blob.tar
tar -xf blob.tar
bandit12@bandit:/tmp/tmp.z91sOImHRk$ ls
blob.tar  data5.bin  data.txt
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv data5.bin blob
bandit12@bandit:/tmp/tmp.z91sOImHRk$ file blob
blob: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv blob blob.tar
tar -xf blob.tar
bandit12@bandit:/tmp/tmp.z91sOImHRk$ ls
blob.tar  data6.bin  data.txt
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv data6.bin blob
bandit12@bandit:/tmp/tmp.z91sOImHRk$ file blob
blob: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv blob blob.bz2
bzip2 -d blob.bz2
bandit12@bandit:/tmp/tmp.z91sOImHRk$ file blob
blob: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv blob blob.tar
tar -xf blob.tar
bandit12@bandit:/tmp/tmp.z91sOImHRk$ ls
blob.tar  data8.bin  data.txt
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv data8.bin blob
bandit12@bandit:/tmp/tmp.z91sOImHRk$ file blob
blob: gzip compressed data, was "data9.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/tmp.z91sOImHRk$ mv blob blob.gz
gzip -d blob.gz
bandit12@bandit:/tmp/tmp.z91sOImHRk$ file blob
blob: ASCII text
bandit12@bandit:/tmp/tmp.z91sOImHRk$ cat blob
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
bandit12@bandit:/tmp/tmp.z91sOImHRk$
```

# Notas
aqui si no supe como se hacia solo 
# Referencias
https://en.wikipedia.org/wiki/Hex_dump
https://mayadevbe-me.translate.goog/posts/overthewire/bandit/level13/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=tc