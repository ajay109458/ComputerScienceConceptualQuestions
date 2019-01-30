# Computer Science Conceptual Questions

## Difference between big endian v/s little endian? 
Big-Endian (BE) / Little-Endian (LE) are two ways to organize multi-byte words. For example, when using two bytes to represent a character in UTF-16, there are two ways to represent the character 0x1234 as a string of bytes (0x00-0xFF):
```
Byte Index:      0  1
---------------------
Big-Endian:     12 34
Little-Endian:  34 12
```

In order to decide if a text uses UTF-16BE or UTF-16LE, the specification recommends to prepend a Byte Order Mark (BOM) to the string, representing the character U+FEFF. So, if the first two bytes of a UTF-16 encoded text file are FE, FF, the encoding is UTF-16BE. For FF, FE, it is UTF-16LE.

A visual example: The word "Example" in different encodings (UTF-16 with BOM):
```
Byte Index:   0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15
------------------------------------------------------------
ASCII:       45 78 61 6d 70 6c 65
UTF-16BE:    FE FF 00 45 00 78 00 61 00 6d 00 70 00 6c 00 65
UTF-16LE:    FF FE 45 00 78 00 61 00 6d 00 70 00 6c 00 65 00
```
