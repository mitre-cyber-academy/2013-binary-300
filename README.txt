README 

The red herring challenge consists of an executable that requests a license key and then outputs a flag from a set of 50000 flags. It will always output a flag but only one input will yield the correct flag as well as the string "Congratulations!" The program determines if its the correct flag by checking against an MD5 sum. Participants can extract this sum from the executable using gdb and then brute force the hash by using the 50000 possibilities in the executable, extractable using the strings program. However, the list of flags are all 9 characters long, while flags are only 8 characters long. The MD5 is performed on the first 8 characters of any flag in the list, so brute force will not yield any results of value. This is also extractable from the executable using gdb. 

Solution Files: there's a ruby script that brute forces the md5 hash using the wordlist from the executable. 

Compiling requires openssl-dev by running 'gcc herring.c -lssl -lcrypto -o herring'

To Distribute: dist/herring
