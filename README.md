# Uncommon Error in Factorial Function: Negative Input Handling

This repository demonstrates a subtle error in a factorial function implementation written in Hack.  The function `bar` calculates the factorial using recursion, but fails to gracefully handle negative input.  Instead of raising an exception or indicating an error, it silently returns 0.

This is an uncommon error because it does not immediately crash the program, leading to potential unexpected behavior and hard-to-debug issues.

## The Bug

The `bar` function does not explicitly handle the case where the input `x` is negative.  While the `foo` function (the recursive factorial function) works correctly for non-negative inputs, `bar` does not validate its input before calling `foo`, resulting in undefined behavior.  For negative input, the recursion will continue indefinitely, leading to a stack overflow which is often silent in Hack, in place of a raised exception.

## The Solution

The solution involves adding input validation to the `bar` function. If a negative value is provided, it should raise an exception or return an appropriate error code. This prevents unexpected behavior and makes the function more robust. The updated `bar` function now throws an exception when the input is negative, making the error more apparent.

## How to reproduce the error and run the solution

1. Clone the repository and install Hack.
2. Compile and run `bar.hh`. Negative input will not produce an exception. 
3. Compile and run `barSolution.hh`. Negative input will now raise an exception.