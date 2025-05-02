# computational_theory
## Cathal McHale 
### Prerequisites

Python 3.13.2

Jupyter Notebook (optional but recommended)

## Execution Steps:

Clone the repository or copy the script.
- git clone https://github.com/Cathal-McHale/computational_theory.git
Run the Python script using:
Jupyter Notebook and run each cell individually or run all.


# Task 1: Binary Operations in Python
This task focuses on implementing and understanding low-level bitwise operations that are foundational in cryptographic algorithms, most notably the SHA-2 (Secure Hash Algorithm 2) family. These operations are essential because modern cryptographic functions rely heavily on bit manipulation to ensure data diffusion and confusion — core principles in cryptographic security. By simulating these operations in Python, this task deepens your understanding of how cryptographic primitives work at the binary level.
## Features Implemented
### Bitwise Left Rotation (rotl)
- Rotates bits of a 32-bit integer to the left.
- Circular Shift – Wikipedia

### Bitwise Right Rotation (rotr)
- Rotates bits to the right, mimicking hardware-level logic.

### Binary Representation
- Displays binary output padded to 32 bits.
- Bitwise Operators – W3Schools

### Choose Function (ch)
- Performs conditional selection using: (x & y) ^ (~x & z)
- SHA-2 – Wikipedia
- NIST FIPS 180-4

### Majority Function (maj)
- Returns the majority bit from x, y, z.
- Majority Function – Wikipedia

# Task 2: Hash Function Conversion
This task involves implementing a classic string hash function originally written in C by Brian Kernighan and Dennis Ritchie in The C Programming Language. The purpose of the function is to efficiently map strings to integers — a foundational step in constructing hash tables and dictionaries.

The original C code iterates over each character of a string, applying a polynomial rolling hash computation:

**unsigned hash(char *s) {**
    **unsigned hashval;**
    **for (hashval = 0; *s != '\0'; s++)**
        **hashval = *s + 31 * hashval;**
    **return hashval % 101;**
**}**


### Features Implemented
- Custom Hash Function (hash_kr)
- Converts strings to integer hash values using:

***hashval = ord(char) + 31 * hashval***
***return hashval % 101***
### Analysis
- 31: Prime number for minimising collisions.

- 101: Prime modulus to map hash values into a fixed-size table.

### References
- Hash Functions – Real Python
- Rabin–Karp Algorithm
- Modular Hashing – Wikipedia

# Task 3: SHA-256 Padding
This task implements the message padding procedure specified in the SHA-2 family of hash functions, specifically SHA-256. The goal of the padding is to prepare an arbitrary-length input so that it can be processed in fixed-size 512-bit (64-byte) blocks by the compression function.

### Features Implemented
- Reads a file’s content and pads it according to SHA-256 rules:
- Appends 0x80 (a single 1 bit)
- Pads with 0x00 until message is 64 bits short of 512-bit block
- Appends original message length in 64-bit big-endian

### References
- SHA-2 – Wikipedia
- FIPS PUB 180-4

# Task 4: Prime Number Generation
This task explores and compares two classical algorithms for generating the first 100 prime numbers. Prime number generation is a foundational concept in computer science and cryptography, underpinning many systems in secure communications, hashing, and number theory.

## Features Implemented
### Sieve of Eratosthenes
- Marks non-primes in a boolean array
- Efficient: O(n log log n)

### Trial Division
- Checks each number’s divisibility up to √n
- Simpler, but slower: O(n √n)

### References
- Sieve of Eratosthenes – Wikipedia
- Trial Division – Wikipedia

# Task 5: Square Root Fractional Bits
This task replicates a key step in the initialisation of the SHA-2 family of cryptographic hash functions: extracting mathematical constants derived from irrational numbers. Specifically, it involves computing the first 32 bits of the fractional part of the square roots of the first 100 prime numbers.

### Features Implemented
- Computes square roots using math.sqrt()
- Extracts fractional part using % 1

### Converts to binary:
***int((math.sqrt(prime) % 1) * (2 ** 32))***
### References
- SHA-2 Constants – Wikipedia
- IEEE 754 Format
- The Prime Pages


# Task 6: SHA-256 Proof of Work
This task simulates the proof-of-work concept used in blockchain and cryptographic systems by searching for English word(s) whose SHA-256 hash starts with the highest number of leading zero bits.

## Features Implemented
- Uses nltk.corpus.words for dictionary input
- Hashes words using SHA-256
- Converts hashes to binary
- Counts leading zero bits and returns top result(s)
- Validates dictionary inclusion

### Code Concept
***bin_hash = bin(int(hash_hex, 16))[2:].zfill(256)***
***leading_zeros = len(bin_hash) - len(bin_hash.lstrip('0'))***

### References
- NLTK Words Corpus
- Python hashlib
- Proof-of-Work – Wikipedia

# Task 7: Turing Machine – Binary Increment
This task implements a basic Turing Machine that performs binary incrementation—adding 1 to a binary number. The machine starts at the left-most non-blank symbol on the tape and reads to the right, treating the right-most digit as the least significant bit (LSB), just as in standard binary arithmetic.

## Features Implemented
- Scans tape from left to right
- Flips trailing 1s to 0 until a 0 is found
- Flips the first 0 to a 1, completing the increment

### E.g.
***Input Tape  : 100111***
***Output Tape : 101000***
## References
- Turing Machine – Wikipedia

# Task 8: Bubble Sort Comparison Count
This task investigates the computational complexity of the Bubble Sort algorithm by analysing the number of comparisons required to sort every permutation of the list:
**L = [1, 2, 3, 4, 5]**
The goal is to highlight how the input order affects the performance of the algorithm in terms of comparison count, a fundamental metric in algorithm analysis.

## Features Implemented
- Generates all 5! = 120 permutations using itertools.permutations
- Sorts each permutation using Bubble Sort

### Tracks and prints:
- Comparisons per permutation
- Minimum, maximum, and average comparisons
- Permutations that cause best and worst cases

Output E.g.
***(1, 2, 3, 4, 5) -> Comparisons: 10***
***(5, 4, 3, 2, 1) -> Comparisons: 10***

### Average comparisons: 10.00

## References
- Bubble Sort – GeeksforGeeks
- Big O Cheat Sheet
- MIT 6.006 – Algorithms

## Task 1: Binary Operations

- Circular Shift – Wikipedia: https://en.wikipedia.org/wiki/Circular_shift

- Bitwise Operators in Python – W3Schools: https://www.w3schools.com/python/python_operators.asp

- SHA-2 – Wikipedia: https://en.wikipedia.org/wiki/SHA-2

- NIST FIPS 180-4 (SHA-2 Standard): https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf

- NIST Secure Hashing Project: https://csrc.nist.gov/projects/secure-hashing

- Majority Function – Wikipedia: https://en.wikipedia.org/wiki/Majority_function

- Binary Representation – GeeksforGeeks: https://www.geeksforgeeks.org/binary-representation-of-a-given-number/

## Task 2: Hash Function Conversion

- Hash Functions in Python – Real Python: https://realpython.com/python-hash-functions/

- Modular Hashing – Wikipedia: https://en.wikipedia.org/wiki/Hash_function

- Rabin–Karp Algorithm – Wikipedia: https://en.wikipedia.org/wiki/Rabin%E2%80%93Karp_algorithm

## Task 3: SHA-256 Padding

- SHA-2 – Wikipedia: https://en.wikipedia.org/wiki/SHA-2

- FIPS PUB 180-4 – NIST (PDF): https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf

## Task 4: Prime Number Generation

- Sieve of Eratosthenes – Wikipedia: https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes

- Trial Division – Wikipedia: https://en.wikipedia.org/wiki/Trial_division

## Task 5: Square Root Fractional Bits

- The Prime Pages – UTM: https://primes.utm.edu/

- IEEE 754 Floating-Point Standard – Wikipedia: https://en.wikipedia.org/wiki/IEEE_754

- SHA-2 – Wikipedia (Constants Reference): https://en.wikipedia.org/wiki/SHA-2

## Task 6: SHA-256 Proof of Work

- Python hashlib – Official Docs: https://docs.python.org/3/library/hashlib.html

- NLTK Words Corpus – API Docs: https://www.nltk.org/api/nltk.corpus.html

- Proof-of-Work – Wikipedia: https://en.wikipedia.org/wiki/Proof_of_work

## Task 7: Turing Machine

- Turing Machine – Wikipedia: https://en.wikipedia.org/wiki/Turing_machine
- https://python-course.eu/applications-python/turing-machine.php#:~:text=final%22%20and%20halts.-,Implementation%20of%20a%20Turing%20machine%20in%20Python,we%20can%20have%20negative%20indices.
- Adding a number by 1:  https://stackoverflow.com/questions/30544560/a-turing-machine-that-adds-one-to-a-binary-number
## Task 8: Bubble Sort Complexity

- Bubble Sort – GeeksforGeeks: https://www.geeksforgeeks.org/bubble-sort/

- MIT OpenCourseWare – 6.006 Introduction to Algorithms: https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-fall-2011/

- Big O Cheat Sheet: https://www.bigocheatsheet.com/

### General Python & Tooling

- Python Official Documentation: https://docs.python.org/3/

- Stack Overflow – General Programming Help: https://stackoverflow.com/

- GeeksforGeeks – Python Index: https://www.geeksforgeeks.org/python-programming-language/