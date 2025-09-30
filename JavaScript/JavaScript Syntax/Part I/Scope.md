# SCOPE

Scope defines where variables can be accessed or referenced. While some can be accessed from anywhere within a program, others may only be available in a specific context.

# Blocks & Scope

A block is the code found inside a set of curly braces {}. A block can define the scope of variables.

# Global Scope

Scope is the context in which our variables are declared. We think about scope in relation to blocks because variables can exist either outside of or within these blocks.

In the *global* scope the variables are declared outside of code blocks. These are *global variables*. Because of this they can also be accessed by any code in the program, including in blocks.

# Block Scope

When a variable is defined inside a block of code it is only accessible to that block. These variables are called *local variables*.

# Scope Pollution

Scope pollution occurs when we have too many variables in the global namespace, or when we reuse variables across different scopes. Scope pollution makes it difficult to keep track of our different variables and sets us up for potential accidents.
Globally scoped variables can collide with other variables that are more locally scoped, causing unexpected behavior in our code.

An example of this:
<br>

```JS
let num = 50;

const logNum = () => {
  num = 100; // Take note of this line of code
  console.log(num);
};

logNum(); // Prints 100
console.log(num); // Prints 100
```

### Tightly scoping variables will greatly improve code in several ways:

* It will make the code more legible since the blocks will organize the code into discrete sections.
* It makes the code more understandable by clarifying which variables are associated with different parts of the program, rather than having to keep track of them line by line!
* It’s easier to maintain tightly scoped code, as it will be modular.
* It will save memory because variables with block scope will cease to exist after the block finishes running.

# SUMMARY

* Scope refers to where variables can be accessed throughout the program, and is determined by where and how they are declared.
* Blocks are statements that exist within curly braces {}.
* Global scope refers to the context within which variables are accessible to every part of the program.
* Global variables are variables that exist within the global scope.
* Block scope refers to the limited reach of variables that are only available within the specific code block where they are defined.
* Local variables are variables that exist within the block scope.
* Global namespace is the space in our code that contains globally scoped information.
* Scope pollution is when too many variables exist in a namespace or variable names are reused.