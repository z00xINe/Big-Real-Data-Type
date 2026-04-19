# BigReal: Arbitrary-Precision Decimal Arithmetic Library

## Overview
A custom C++ implementation designed to handle high-precision real number calculations that exceed the limits of standard floating-point data types. The `BigReal` class stores integer and fractional components separately using deque-based structures, enabling manual digit-by-digit arithmetic with precise carry and borrow management.

## Features
- Supports arbitrarily large positive and negative real numbers
- Manual implementation of addition and subtraction with full carry/borrow propagation
- Comparison operators (`<`, `>`, `==`) for precise numeric evaluation
- Robust input validation and string parsing for real number initialization
- Operator overloading for intuitive arithmetic and stream output (`<<`)
- Copy constructor and utility methods (`size()`, `sign()`)
- Clean separation of whole and fractional parts to prevent precision loss

## Technologies Used
- Language: C++
- Standard Libraries: iostream, string, deque
- Compiler: Compatible with any C++11 or higher compliant compiler (GCC, Clang, MSVC)

## Setup and Usage
1. Place `BigReal.h` and `BigReal.cpp` in your project directory.
2. Include the header in your source file:
```cpp
#include "BigReal.h"
```
3. Instantiate and perform operations:
```
BigReal num1("+12345.6789");
BigReal num2("-987.12");
BigReal result = num1 + num2;
std::cout << result << std::endl;
```
4. Compile with your preferred C++ compiler:
```
g++ main.cpp BigReal.cpp -o BigRealApp
./BigRealApp
```

## Architecture Notes

- Stores digits as character sequences in std::deque for efficient front/back operations and dynamic resizing.
- Implements alignment padding and sign-aware arithmetic logic to handle mixed positive/negative operations correctly.
- Validates input format during construction, rejecting malformed strings and enforcing a consistent signed decimal representation.

## Limitations and Future Work

- Multiplication, division, and exponentiation are not currently implemented.
- Scientific notation parsing and configurable precision truncation could be added.
- Unit testing and boundary case validation (e.g., leading zeros, trailing decimal alignment) are recommended for production use.
