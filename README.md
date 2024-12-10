# F# Mutable Variable Swapping Bug

This repository demonstrates a common error in F# related to the behavior of mutable variables within functions.  The `swap` function attempts to swap the values of two mutable variables, `x` and `y`.  However, due to F#'s behavior with mutable variables, this doesn't work as expected.

**The Problem:**
F#'s mutable variables are not passed by reference, but by value.  Thus, the `swap` function receives copies of `x` and `y`, altering only the local copies, not the original variables.

**The Solution:**
The solution involves explicitly returning the swapped values, and reassigning them in the caller.

This example highlights a crucial aspect of F#'s functional paradigm and how mutable variables work within it. Understanding this difference is important for writing correct and predictable F# code.