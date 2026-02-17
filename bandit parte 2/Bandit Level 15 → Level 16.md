# Bandit Level 15 → Level 16
# Descripción
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL/TLS encryption.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**
# Solución
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

C:\Users\ero33>ssh -i sshkey.private bandit15@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit15@bandit.labs.overthewire.org's password:

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

bandit15@bandit:~$ ls
bandit15@bandit:~$ cat /etc/bandit_pass/bandit15
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 3CF0B658F4CE6E900C9AE05430A13AFC4CEEEA129181FC61C4268FFB4082FFB9
    Session-ID-ctx:
    Resumption PSK: 5119B63B84C3D3D14D9DD36238CE8E2502254759B2B274903E05213C56A4F29A2FED701C60DFDB2EA66D7A9235C94FE0
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 9e e4 b9 b6 dd c1 ab 16-88 78 31 ae 0b 36 ae 89   .........x1..6..
    0010 - ed 13 a8 78 4f 31 52 a8-9a 09 ae dc e6 a9 e4 f6   ...xO1R.........
    0020 - 3f a2 36 ac 7a df 90 f9-a6 6b eb 54 9e 8b 78 48   ?.6.z....k.T..xH
    0030 - 9a 63 87 84 af 0e 93 8c-13 eb 08 0f f2 f9 ae 99   .c..............
    0040 - 3e 2d 64 a8 8f 15 fe ba-64 48 a7 0b f0 e3 a0 78   >-d.....dH.....x
    0050 - 3c 9f 03 be 49 8d 45 db-2f 46 bf ab f2 4c 4d be   <...I.E./F...LM.
    0060 - cc 72 36 3a 91 42 c7 6f-a5 0b 7f 94 2b 15 5d 37   .r6:.B.o....+.]7
    0070 - 16 15 c6 4c 4f a6 8e ee-40 d5 1e 80 bb 01 d7 7f   ...LO...@.......
    0080 - 9b 8a 2d 30 27 1d 5d de-7c 71 e3 de 9c e6 0b 2a   ..-0'.].|q.....*
    0090 - 47 cc f0 ba b2 e3 1b e2-f0 12 02 f5 c9 b3 6f eb   G.............o.
    00a0 - fa 82 7c 5a fb e5 98 ff-b5 3f c9 03 2d 83 df 71   ..|Z.....?..-..q
    00b0 - a2 e3 64 e6 b8 a4 c3 46-5a 67 42 1f 10 31 f1 dd   ..d....FZgB..1..
    00c0 - 15 9b 85 cc e5 81 6a 37-54 48 5f 4e 1a c0 a3 c7   ......j7TH_N....
    00d0 - 65 4b 3e 5a c2 97 c2 a4-49 46 b3 87 b0 e1 c7 55   eK>Z....IF.....U

    Start Time: 1771298140
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 979FBE76217D01EE81339E411F8ED1601A8A90628D861B67C15C02F7B7D2AA82
    Session-ID-ctx:
    Resumption PSK: A593C216733BEF118C60DB19A90FB6244AE0AB1BB6F1A57B368BDD31820419DFB288CE6388C8307170474F75C16485D7
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 9e e4 b9 b6 dd c1 ab 16-88 78 31 ae 0b 36 ae 89   .........x1..6..
    0010 - 4a c4 81 79 60 25 d9 ff-c6 32 ee 77 48 f9 e2 0f   J..y`%...2.wH...
    0020 - ca 34 d0 ea a5 b4 ec 11-04 ab 24 b8 4a ba 27 bc   .4........$.J.'.
    0030 - 47 01 36 b1 69 fa 51 4e-ac 3d a0 a6 47 71 d0 fb   G.6.i.QN.=..Gq..
    0040 - 53 4b 4b 33 64 39 0b 08-df 78 8d 44 13 ea 9a b1   SKK3d9...x.D....
    0050 - f4 0d a7 1e 9a 74 da ef-8c a0 9a 68 33 41 bc 2e   .....t.....h3A..
    0060 - 14 2d cb e7 b4 fd b6 f8-b3 e8 a3 5b 16 fc 72 07   .-.........[..r.
    0070 - 0a 59 19 4e 51 b9 df 19-1d 60 05 16 fc 96 d8 69   .Y.NQ....`.....i
    0080 - fe 98 95 13 fe b2 e1 21-76 d6 37 9b 05 46 2b ae   .......!v.7..F+.
    0090 - 01 81 7a 67 e5 71 15 fa-2f a8 83 34 de fb 43 6b   ..zg.q../..4..Ck
    00a0 - fb 8a 4a 7d ec 4e 49 eb-a9 be 44 f4 f2 5b 89 a0   ..J}.NI...D..[..
    00b0 - 1b 36 59 01 7c 98 c2 f4-ad 9f 70 f9 90 b1 ca 34   .6Y.|.....p....4
    00c0 - 48 d3 20 62 d5 b0 3b ff-f4 b8 24 e8 2b f8 9c a7   H. b..;...$.+...
    00d0 - 04 5f 75 22 5d b3 61 d4-47 76 1f 98 10 e1 58 63   ._u"].a.Gv....Xc

    Start Time: 1771298140
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

closed
bandit15@bandit:~$
```

# Notas
# Referencias
