# binhexa
# Descripción
How well can you perfom basic binary operations? Start searching for the flag here `nc titan.picoctf.net 61032`
# Solución
picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_675602ae}

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

erasmo-picoctf@webshell:~$ nc titan.picoctf.net 61032

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 01101101
Binary Number 2: 00001100


Question 1/6:
Operation 1: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00001100
Correct!

Question 2/6:
Operation 2: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01111001
Correct!

Question 3/6:
Operation 3: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01101101
Correct!

Question 4/6:
Operation 4: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00000110
Correct!

Question 5/6:
Operation 5: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10100011100
Correct!

Question 6/6:
Operation 6: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 11011010
Correct!

Enter the results of the last operation in hexadecimal: DA

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_675602ae}

```

# Notas
# Referencias
