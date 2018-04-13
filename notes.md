
### Finite Fields

#### What is a finite field:
- It is a set of numbers
- Finite set
- Four operations in Finite fields ( addition, subtraction, multiplication and division)
  - Considered closed under addition, subtraction, multiplication and division except division by 0)
  - These are operations we are going to define
  - Exception: Division by zero;
  - Define division in such a way that it belongs in the finite field
  - Closed means that if you take two elements perform an operation among them, they belong in the same finite field.
- Used at a variety of places but mainly for elliptic curve cryptography
- Prime fields are most interesting

#### Example
Prime Field of 19 (Denoted as F~19~)
- F~19~ = {0, 1, 2, ... , 18}
- F~97~ = {0, 1, 2, ... , 96}
- F~48947~ = {0, 1, 2, ... , 48946}

The field is every number upto a particular number.
Since, there's zero, the field ends one before the actual number to stay consistent with the number of digits.

### Modular Arithmetic
Some people call it remainder math

remainder is modular Arithmetic

- 11 / 7 = 1 R 4
- 38 / 12 = 3 R 2

Thinking about it as a clock might be helpful
Along the lines of what hour is it supposed to be 38 hours from now
![image](https://ka-perseus-images.s3.amazonaws.com/3a2cb32acda2b6b63f88c61b8def97c0c1185767.jpg)

#### Addition and Subtraction:
Relatively the same as modulo P Arithmetic (F~19~)

- 11 + 6 = 17 % 19 = 17 is the same as 11 + 6 = 17 mod 19 = 17
=> 17 - 6 = 11 % 19 = 11 is the same as 17 - 6 = 11 mod 19 = 11

  It is the same addition and subtraction as it remains under 19 but however as the addition goes above 19,

- 8 + 14 = 22 % 19 = 3 is the same as 8 + 14 = 22 mod 19 = 3

   In this 8 + 14 equals 22 which in the finite field of 19 results in 3.
   This can be obtained by dividing or counting the number of rounds of 19 within 22 and the remainder would be the answer

    3 is under the finite field

- 4 - 12 = -8 % 19 = 11
    In this example, the sum of 4 and -12 equals -8 which is outside the finite field of 0 - 19. The difference between -8 and 19 that remains is 11 which ends up being the answer in this case.

#### Multiplication and Exponentiation
Relatively the same as modulo P Arithmetic (F~19~)

- 2 * 4 = 8 % 19 = 8
  - two times 4 equals 8 which in the finite field of 19 returns 8 as remainder
- 7 * 3 = 21 % 19 = 2
  - 7 times 3 equals 21 which in the finite field of 19 returns 2 as remainder.
- 11^3^ = 1331 % 19 = 1
  - 11 multiplied by itself yields 1331 which in the finite field of 19 equates to 1 implying that 1330 is completely divisible by 19 (70 times).

> Python: pow(11, 3, 19) == 1
This is the python function that lets you do modulo functions.
This above stated implementation of the function is effectively 11^3^ mod 19

#### Division:
Defined as the inverse of multiplication (F~19~)

- 2 * 4 = 8 => 8 / 4 = 2
  - 2 times 4 equals 8
  - This implies 8 when divided by four results in 2
- 7 * 3 = 2 => 2 / 3 = 7
  - 7 times 3 results in 21 which in a finite field bounded by 0 and 18 would result in 2 since the remainder of 21 in a finite field of 19 would result in 2.
  - This implies that 2 when divided by 3 in a finite field of 19 results in 7.
- 15 * 4 = 3 => 3 / 4 = 15
  - 15 times 4 equals 60 which in the finite field bounded by 0 and 18 (essentially mod 19 or F~19~) results in 3.
  - This implies that 3 when divided by 4 in a finite field of 19 results in 15.
- 11 * 11 = 7 => 7 / 11 = 11
  - 11 times 11 equals 121 which in the finite field of 19 bounded by 0 and 18 results in 7.
  - Division being the inverse of multiplication implies that 11 when added to itself (11 times) reaches remainder of 7 within a finite field of 19 bounded by 0 and 18.

> Division within finite fields are bounded and restrictive.
> Multiplication can be seen as the number of times the same number is added to itself.
> Division is the inverse of multiplication.
> Division is essentially subtracting/adding the same number over and over again until the remainder is attained. 
