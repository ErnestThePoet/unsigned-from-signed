# Unsigned From Signed
This project implements common unsigned 32-bit and 64-bit integer operations using **32-bit signed** integer operations only.

## Why I created this project
I have an interest in implementing cryptography algorithms on the [IR Virtual Machine](https://github.com/ErnestThePoet/ir-virtual-machine) platform using C--, which is a small subset of C that only supports few 32-bit signed integer operations: add, sub, mul, div and comparison. In the very beginning, the first challenge I faced was to implement unsigned integer operations, some of which are markedly different from signed counterparts. After some hard efforts, I finished my implementations and shared them in this repository.  
Never mind the long and ugly variable names; my hand-written compiler needs them because it does not accept repeated variable names in a file.

## Usage
Just include the header `unsigned_op.h`. Call `init_two_powers()` first before calling all other functions.  
Note that all 64-bit integers are stored in two-element `int` arrays, with index `0` element containing the 4 most significant bytes.
## Unsigned integer operations implemented
|Operation|32-Bit|64-Bit|
|---------|------|------|
|Right shift|√|√|
|Left shift|√|√|
|Get bit count|√|√|
|Compare|√|√|
|Negative|√|√|
|Full addition (carry output)|√|√|
|Addition|×|√|
|Full subtraction (borrow output)|√|√|
|Subtraction|×|√|
|Full Multiplication (width*2)|√|×|
|Multiplication|×|√|
|Division and modulo|√|√|
|Division|√|√|
|Modulo|√|√|

### Notes
- 32-bit unsigned addition, subtraction and multiplication are not implemented, because signed operations yield exactly the same results.
- 64-bit unsigned full multiplication is not implemented because that will yield 128-bit output.
