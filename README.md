# BigInt Class

[![C++](https://img.shields.io/badge/C%2B%2B-20/23/26-blue.svg)](https://isocpp.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen.svg)]()

A **header-only** C++ BigInt class that can store arbitrarily large integers beyond the limits of built-in types (int, long, long long). Perfect for games, cryptography, and mathematical applications where large numbers are needed.

## Features

-  **Arbitrary Precision** - Store numbers of any size
-  **Header-Only** - Just include the header and use it
-  **No External Dependencies** - Pure standard library
-  **Type-Safe** - Strong type checking with concepts
-  **Exception Safe** - Proper error handling

## Quick Example

```cpp
#include "bigint.hpp"
#include <iostream>

int main() {
    // Create BigInts from strings, integers, or literals
    BigInt a = "12345678901234567890";
    BigInt b = 9876543210;
    BigInt c = "99999999999999999999"_big;  // User-defined literal
    
    // Arithmetic operations
    BigInt sum = a + b;
    BigInt product = a * b;
    BigInt power = a ^ 10;  // a raised to the 10th power
    
    // Mathematical utilities
    BigInt gcd_result = BigInt::gcd(a, b);
    BigInt sqrt_result = BigInt::sqrt(a);
    BigInt fact = BigInt::factorial(100);  // 100! 
    
    // Display
    std::cout << "a = " << a << "\n";
    std::cout << "b = " << b << "\n";
    std::cout << "Sum = " << sum << "\n";
    std::cout << "GCD = " << gcd_result << "\n";
    
    return 0;
}
```

## Constructors
### Constructor	Example	Description
- BigInt()	BigInt x;	Default constructor (value = 0)
- BigInt(int)	BigInt x = 123;	From integer
- BigInt(long)	BigInt x = 123L;	From long
- BigInt(long long)	BigInt x = 123LL;	From long long
- BigInt(const char*)	BigInt x = "123";	From C-string
- BigInt(const std::string&)	BigInt x = std::string("123");	From std::string
- BigInt(std::string_view)	BigInt x = "123";	From string_view
  
## User-Defined literals
```cpp
auto x = "12345678901234567890"_big;
auto y = 123_big;
```

# Supported Operators
## Arithmetic Operators
### Operator	Description	Example

-  Addition	BigInt sum = a + b;
- Subtraction	BigInt diff = a - b;
- Multiplication	BigInt prod = a * b;
- Division	BigInt quot = a / b;
- Modulo	BigInt rem = a % b;
- Power	BigInt pow = a ^ 10;
- (unary)	Negation	BigInt neg = -a;
- (unary)	Unary plus	BigInt pos = +a;
  
## Comparison Operators
### Operator	Description	Example
- ==	Equality	if (a == b) { ... }
- !=	Inequality	if (a != b) { ... }
- <	Less than	if (a < b) { ... }
- \>	Greater than	if (a > b) { ... }
- <=	Less than or equal	if (a <= b) { ... }
- \>=	Greater than or equal	if (a >= b) { ... }
  
## Compound Assignment
### Operator	Description	Example
- +=  Add and assign	a += b;
- -=	Subtract and assign	a -= b;
- *=	Multiply and assign	a *= b;
-  /=	Divide and assign	a /= b;
- %=	Modulo and assign	a %= b;
- ^=	Power and assign	a ^= 10;

## Increment/Decrement
### Operator	Description	Example
- ++ (prefix)	Pre-increment	++a;
- ++ (postfix)	Post-increment	a++;
- -- (prefix)	Pre-decrement	--a;
- -- (postfix)	Post-decrement	a--;
  
## Stream Operators
### Operator	Description	Example
- <<	Output	std::cout << a;
- \>>	Input	std::cin >> a;

## Mathematical Functions
### Function	Description	Example
- gcd(a, b)	Greatest Common Divisor	BigInt g = BigInt::gcd(a, b);
- lcm(a, b)	Least Common Multiple	BigInt l = BigInt::lcm(a, b);
- abs(n)	Absolute Value	BigInt abs = BigInt::abs(n);
- sqrt(n)	Square Root (floor)	BigInt root = BigInt::sqrt(n);
- pow_10(exp)	Power of 10	BigInt pow = BigInt::pow_10(5);
- Member Functions
- Function	Description	Example
- toString()	Convert to string	std::string s = x.toString();
- toInt()	Convert to int (throws on overflow)	int i = x.toInt();
- toLong()	Convert to long (throws on overflow)	long l = x.toLong();
- toLongLong()	Convert to long long (throws on overflow)	long long ll = x.toLongLong();
- isZero()	Check if zero	if (x.isZero()) { ... }
 
