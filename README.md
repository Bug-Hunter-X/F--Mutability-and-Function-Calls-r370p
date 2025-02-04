# F# Mutability and Function Calls

This example demonstrates a potential issue with mutable variables in F# when used within functions.

## Bug Description
The `add` function calculates the sum of `x` and `y`. However, modifying `x` and `y` *after* the initial function call does not affect the value of `z`. This behavior might be unexpected if you anticipate that `z` would reflect the changes made to `x` and `y`.

## How to Reproduce
1.  Compile and run the code in `bug.fs`.
2.  Observe the output. The second `printf` statement will print the initial sum of x and y rather than the updated sum.

## Solution
The solution involves understanding how F# handles mutable variables and function calls.  The `add` function computes the sum based on the values of `x` and `y` at the time it was called. Subsequent changes to these variables do not affect `z`.
See the corrected code in `bugSolution.fs`