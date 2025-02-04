# JavaScript Closure Issue in setTimeout

This repository demonstrates a common JavaScript closure issue related to the use of `setTimeout` within a loop.

## Bug Description
The `myFunction` uses a `for` loop and `setTimeout` to log the value of `i` after a 1-second delay.  Due to closure, one might expect that each iteration of the loop logs the correct value of `i` at that iteration. However, due to the way closures and asynchronous functions work in JavaScript, all iterations end up logging the final value of `i` (which is 10). This is because the `setTimeout` callbacks don't capture the value of `i` at each iteration but rather when they are executed after the loop has completed. 

## Bug Solution
The solution involves using an immediately invoked function expression (IIFE) to create a new scope for each iteration, effectively capturing the correct value of `i` for each callback.