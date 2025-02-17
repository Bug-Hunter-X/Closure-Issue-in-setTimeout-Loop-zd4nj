# Closure Issue in setTimeout Loop

This example demonstrates a common issue in JavaScript when using closures within `setTimeout` loops. The expected behavior is to print numbers 0 through 9 with a one-second delay. However, due to the way closures work in JavaScript, all logs show 10.

## Bug Description
The variable `i` is not captured at each iteration of the loop. By the time the `setTimeout` callbacks finally execute, the loop has already completed, and `i` holds its final value of 10.

## Solution
To fix this, you need to create a new scope for each iteration using an immediately invoked function expression (IIFE) or `let` in the loop, to preserve the value of i for each iteration.