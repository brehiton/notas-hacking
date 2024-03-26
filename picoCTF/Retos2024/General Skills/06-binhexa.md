## Objetivo
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 56491`
## Pistas

## Solucion
```
┌──(aimar㉿Aimar)-[~]
└─$ nc titan.picoctf.net 56491

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 01000111
Binary Number 2: 01010111


Question 1/6:
Operation 1: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01000111
Correct!

Question 2/6:
Operation 2: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 1100000100001
Incorrect. Try again
Enter the binary result: 6177

Incorrect input. Provide the right input
Enter the binary result: 10001110
Correct!

Question 3/6:
Operation 3: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01010111
Correct!

Question 4/6:
Operation 4: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00101011
Correct!

Question 5/6:
Operation 5: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10111001
Incorrect. Try again
Enter the binary result: 10011110
Correct!

Question 6/6:
Operation 6: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1100000100001
Correct!

Enter the results of the last operation in hexadecimal: 31 31 30 30 30 30 30 31 30 30 30 30 31

Incorrect input. Provide the right input!

Enter the results of the last operation in hexadecimal: C101
Incorrect answer!

Enter the results of the last operation in hexadecimal: 1821

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}
```
## Notas adicionales 

## Referencias 