# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
~~~
import numpy as np
text = input("Enter the plaintext message: ")
key_string = input("Enter the key matrix (space-separated values, row-wise): ")
key_values = list(map(int, key_string.strip().split()))
size = int(len(key_values) ** 0.5)
key_matrix = np.array(key_values).reshape(size, size)
if len(text) % size != 0:
    text += 'X' * (size - (len(text) % size))
text = text.upper().replace(" ", "")
text_matrix = []
for i in range(0, len(text), size):
    row = [ord(c) - ord('A') for c in text[i:i+size]]
    text_matrix.append(row)
text_matrix = np.array(text_matrix)
result_matrix = np.dot(text_matrix, key_matrix)
result_matrix = np.mod(result_matrix, 26)
cipher_text = ""
for row in result_matrix:
    for val in row:
        cipher_text += chr(val + ord('A'))
print("Encrypted message:", cipher_text)
~~~
## OUTPUT
<img width="1920" height="1200" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/df85a5f4-fd78-48a6-8ea8-782af25c58ee" />
## RESULT

Thus,hill cipher has been successfully implemented.
