# Encrypt_Decrypt
Write a program that reads from the keyboard a small password and then offers two options: 1. enter your name and a filename to save or 2. enter a file name to load.

With the option 1 proceed to save to the file an encrypted version of your name (details below), with the option 2 proceed to load the information from the file and decrypt the name and print it to the screen.

The options 1 and 2 are in reverse (1 saves the encrypted information to the file, 2 decrypts the information from the file).

Details of the encryption:

Say your name is Andrei  and you chose the password 1234, then you do XOR between the ASCII code for A (first letter in your name) and the ASCII code for 1(first letter in your password), I will denote this operation (A,1)

then you do XOR between n and 2 (n,2) (second letter in your name with second letter in password) and so on, thus we will have the following operations to perform:

(A,1) (n,2) (d,3) (r,4) (e,1) (i,2).

Obviously, if you would choose the password qwer then the XOR operations will be between the following pairs:

(A,q)(n,w)(d,e)(r,r)(e,q)(i,w).

The trick is that the encrypted text can be decrypted due to the following property of XOR: A XOR B=C; C XOR B=A, thus  if I have the results of the XOR operations in the file (and this is your name encrypted) then it is sufficient to do XOR with the same password (with the same ASCII codes) and I will get back the original string.

For example, with the first password, (A XOR 1) XOR 1 =A, (n XOR 2) XOR 2=n and so on:

((A,1),1) ((n,2),2) ((d,3),3) ((r,4),4) ((e,1),1) ((i,2),2)= A n d r e i.
