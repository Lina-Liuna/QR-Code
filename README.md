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

Data Encoding: Each mode uses a different method for converting the input text into a string of bits. 
Entire data encoding step:
1. Choose the Error Correction Level
L M Q H, the higher the larger.
2. Determine the smallest version for the data
3. Add the mode indicator, Byte Mode 0100(bit), the encoded data start with the appropriate mode indicator.
4. Add the character count indicator, placed after the mode indicator. Count the number of characters in the original input text, then convert that nuber into binary, to pading to make it suit bits long.
5. Encode using the selected mode:
   1. Byte mode encoding:
      1. Convert to ISO 8859-1 or UTF-8
      2. split the string into 8-bit Bytes
      3. Convert each byte into binary pad on the left with 0s to make each one 8-bits long.
6. Error correction coding
   1. Break data codewords into blocks if necessary.
   2. complicated....skip now... 
7. Structure final message.
        

Structure:
Version (1 <= V <= 40)： Size = N * N; N = 4 * V + 17 => N2 modules
example: v = 10, N = 4 * 10 + 17 = 57
So each version is 4 pixels larger than the previous version
See QR code-Structure pic for example.

How to decide QR code mode?
1. Numeric modes: 0-9
2. Alphanumeric mode:  upercase letters
3. Byte mode: double byte
4. Kanji mode 
5. Extended channel interpretation(ECI) mode UTF-8 

How to determine the version of QR Code to be used?

For Alphanumeric:
4 + 9 + 11 * (AlphanumericNum / 2) + (odd = 0, then 0; odd = 1, then 6)
For example:
when you make data that 70 alphanumeric character digits, the error correction Level: L

4 + 9 + 11 * 35 + 0 = 206,

then? hold on...











