# QR-Code
QR Code

Data capacity:
The amount of data that can be stored in the QR code depends on datatype, version, error correction.

datatype: mode, or input character set
version: 1,...40

Encoding:
The format information records two things: 
1. the error correction level and
2. the mask pattern: defind on a grid, i for row, j for column, j % 3 = 0; (i + j)%3 = 0...

Structure:
Version (1 <= V <= 40)： Size = N * N; N = 4 * V + 17 => N2 modules
example: v = 10, N = 4 * 10 + 17 = 57
See QR code-Structure pic for example.
