<img src='./Resources/ErrorDiagram.svg>

A big part of debugging errors is recognizing which piece of information are useful and which aren't. 

# Error Types

### Very common error types:

* SyntaxError: This error will be thrown when a typo creates invalid code — code that cannot be interpreted by the compiler. When this error is thrown, scan your code to make sure you properly opened and closed all brackets, braces, and parentheses and that you didn’t include any invalid semicolons.
* ReferenceError: This error will be thrown if you try to use a variable that does not exist. When this error is thrown, make sure all variables are properly declared.
* TypeError: This error will be thrown if you attempt to perform an operation on a value of the wrong type. For example, if we tried to use a string method on a number, it would throw a TypeError.

# Debugging Errors

### The Process:

1. Run your code. Using the first error’s stack trace, identify the error’s type, description, and location.
1. Go to the file name and line number indicated by the error stack trace. Using the error type and description, identify the bug in your code.
1. Fix the bug and re-run your code.
1. Repeat steps 1-3 until your code no longer throws any errors.

## Locating Silent Bugs

Even if code is error-free, it's not necessarily bug-free.

Use print statements ( console.log() ) to identify what and where is not working correctly.

### The workflow:

1. Print out all starting variables, existing values, and arguments using console.log() at the start of the code. If the values are what you expect, move on to the next piece of logic in the code. If not, you have identified a bug and should skip to step 3.
2. After the next piece of logic in your code, add console.log() statements to ensure updated variables have the values that you now expect and that the block of code is being executed. If that logic is executing properly, continue repeating this step until you find a line not working as expected.
3. Fix the identified bug and run your code again. If it now works as expected, you’ve finished debugging! If not, continue stepping through your code using step 2 until it does.

