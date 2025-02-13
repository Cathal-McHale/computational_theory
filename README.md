# computational_theory

## Prerequisites

Python 3.13.2

Jupyter Notebook (optional but recommended)

## Execution Steps:

Clone the repository or copy the script.

Run the Python script using:
Jupyter Notebook and run each cell individually or run all.


## Task 1
- 32 bits unsigned -(https://www.geeksforgeeks.org/binary-representation-of-a-given-number/)
# Binary Operations in Python

This project demonstrates fundamental binary operations in Python, including bitwise rotations, bit selection, and majority voting. These operations are commonly used in cryptographic applications and low-level computing tasks.

## Features Implemented

# Bitwise Left Rotation (rotl)

- Rotates the bits of a 32-bit unsigned integer to the left by n places.

- Ensures bit shifts stay within 32-bit limits.

- **Reference**: Circular Shift (Wikipedia)

- Bitwise Right Rotation (rotr)

- Rotates the bits of a 32-bit unsigned integer to the right by n places.

- **Reference**: Circular Shift (Wikipedia)

- Binary Representation (bin_representation)

- Returns a 32-bit binary representation of a number as a string.

- **Reference**: Bitwise Operators in Python

# Choose Function (ch)

- Implements the bitwise Choose (CH) operation.

- Selects bits from y where x has bits set to 1 and bits from z where x has bits set to 0.

- Formula: ch(x, y, z) = (x & y) ^ (~x & z)

- **Reference**: SHA-2 (Wikipedia)

# Majority Function (maj)

- Takes a majority vote of bits in x, y, and z.

- Outputs a 1 where at least two of x, y, z have 1’s in position i.

- Formula: maj(x, y, z) = (x & y) ^ (x & z) ^ (y & z)

- **Reference**: Majority Function (Wikipedia)


# Task 2: Hash Functions

This section covers hash functions, specifically implementing and testing a hash function inspired by Brian Kernighan and Dennis Ritchie's C code. We will convert the given C function to Python, test it with different inputs, and analyse the choice of values 31 and 101.

### **Features Implemented**

#### **Hash Function (hash_function)**
- Converts a given string into an integer hash value.
- Uses a rolling hash approach, where each character contributes to the final hash value.
- Ensures values fit within 101 buckets using modular arithmetic.
- **Reference**: [Hash Functions in C and Python](https://realpython.com/python-hash-functions/)

#### **Mathematical Formula**
The hash function is implemented using the formula:
```
hashval = ord(char) + 31 * hashval
hashval = hashval % 101  # Ensuring distribution within 101 buckets
```
- **31 is a prime number**, reducing the risk of hash collisions.
- **101 is also a prime number**, ensuring better distribution when applying the modulus operation.
- The combination of multiplication and modulus makes it efficient for rolling hash algorithms like **Rabin-Karp**.
- **Reference**: [Modular Hashing](https://en.wikipedia.org/wiki/Hash_function)
- [Real Python - Hash Functions](https://realpython.com/python-hash-functions/)
- [Rabin-Karp Algorithm](https://en.wikipedia.org/wiki/Rabin%E2%80%93Karp_algorithm)
- [Modular Hashing](https://en.wikipedia.org/wiki/Hash_function)

## Task 3: SHA-256 Padding
- This section explores the SHA-256 padding, implementing a function to calcualte the correct padding for a given file. The function follows the SHA-256 padding specification to ensure messages are prepared correctly before hashing.

## Features Implemented
### SHA-256 Padding Function
- Reads a file and computes its SHA-256 paddding
- appends:
    - A single 1 bit (0x80 in hex)
    - Enough 0 bits to reach the nearest 512-bit block
    - The original message length as a 64-bit big-endian integer
## References 
- https://en.wikipedia.org/wiki/SHA-2
- https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf

### Mathamatical Concept
***********************************************************
padding = 0x80  # Append '1' bit
zero_padding = (56 - (message_length + 1) % 64) % 64 * 0x00
length_padding = original_length_in_bits (as 64-bit big-endian integer)
***********************************************************
- Ensures message length is a multiple of 512 bits
- Encodes message length to prevent collision vulnerabilities 


# Task 4 Prime Numbers
This section implements two different algorithms to compute the first 1000 prime numbers. the two methods used are:
1. Sieve of Eratosthenes (Efficient for finding many prime numbers)
2. Basic Trial Division (Simpler but slower)

## Features Implemented
### Sieve of Eratosthenes
- Uses a boolean array to mark non-prime numbers
- Iterates through numbers, marking multiples as non-prime
- Time complexity: O(n log log n), efficient for generating large sets of primes.

### Trial Division Method
- Iterates over numbers, testing divisibility by known primes
- Stops checking once a divisor greater than sqrt(n) is reached
- Time Complexity: O(n sqrt(n)), much slower than the sieve method.

### References
-  https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes
-  https://en.wikipedia.org/wiki/Trial_division