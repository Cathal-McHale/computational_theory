# computational_theory

## Prerequisites

Python 3.13.2

Jupyter Notebook (optional but recommended)

Execution Steps

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

- Reference: Circular Shift (Wikipedia)

- Bitwise Right Rotation (rotr)

- Rotates the bits of a 32-bit unsigned integer to the right by n places.

- Reference: Circular Shift (Wikipedia)

- Binary Representation (bin_representation)

- Returns a 32-bit binary representation of a number as a string.

- Reference: Bitwise Operators in Python

# Choose Function (ch)

- Implements the bitwise Choose (CH) operation.

- Selects bits from y where x has bits set to 1 and bits from z where x has bits set to 0.

- Formula: ch(x, y, z) = (x & y) ^ (~x & z)

- Reference: SHA-2 (Wikipedia)

# Majority Function (maj)

- Takes a majority vote of bits in x, y, and z.

- Outputs a 1 where at least two of x, y, z have 1’s in position i.

- Formula: maj(x, y, z) = (x & y) ^ (x & z) ^ (y & z)

- Reference: Majority Function (Wikipedia)