# Function Declarations

```JS
function greetWorld() {
  console.log('Hello, World!');
}
```
<br>

### A function declaration consists of:

* The ***function***  keyword.
* The name of the function, or its identifier, followed by parentheses.
* A function body, or the block of statements required to perform a specific task, enclosed in the function’s curly brackets, { }.

The ***hoisting*** feature in JavaScript allows access to function declarations before they’re defined. However, this isn't good practice so it should be avoided.
<br>

# Calling a Function

We call a function by typing the function name followed by ();
Ex: myFunction();

The function call executes the function body, or all of the statements between the curly braces in the function declaration.
<br>

# Parameters and Arguments
<br>
<img src='/JavaScript/JavaScript Syntax/Resources/function_parameters.svg'>

<br>

Functions can take inputs and use the inputs to perform a task. When declaring a function we can specify its *parameters*.
Parameters allow functions to accept input(s) and perform a task using the input(s). We use parameters as placeholders for information that will be passed to the function when it is called.

In the diagram above, calculateArea() computes the area of a rectangle, based on two inputs, width and height. The parameters are specified between the parentheses as width and height, and inside the function body, they act just like regular variables. width and height act as placeholders for values that will be multiplied together.

When calling a function that has parameters we specify the values inside the (). Example: calculateArea(10,50);

<br>

# Default Parameters 

Default parameters allow parameters to have a predetermined value in case no argument is passed into the function or if the argument is undefined when called.

```JS
function greeting (name = 'stranger') {
  console.log(`Hello, ${name}!`)
}

greeting('Nick') // Output: Hello, Nick!
greeting() // Output: Hello, stranger!
```

Assigning a value to the parameter directly in the function declaration makes that value the default one.
Here's the breakdown as per the course:

* In the example above, we used the = operator to assign the parameter name a default value of 'stranger'. This is useful to have in case we ever want to include a non-personalized default greeting!

* When the code calls greeting('Nick') the value of the argument is passed in and, 'Nick', will override the default parameter of 'stranger' to log 'Hello, Nick!' to the console.

* When there isn’t an argument passed into greeting(), the default value of 'stranger' is used, and 'Hello, stranger!' is logged to the console.

<br>

# Return

When a function is called, the computer will run through the function’s code and evaluate the result. By default, the resulting value is ***undefined***.

<img src='/JavaScript/JavaScript Syntax/Resources/function_return.svg'>

In the code example, we defined our function to calculate the area of a width and height parameter. Then rectangleArea() is invoked with the arguments 5 and 7. But when we went to print the results, we got undefined. 

The reason is we didn't *capture* the output. This is what the keyword ***return*** is used for.

If we add *return area;*** it will capture the result:

```JS

function calculateArea(width, height) {
     const area = width * height ;
     return area;
}
console.log(calculateArea(5, 7))
```

***return*** can be used multiple times within the same function. for example:

```JS
function rectangleArea(width, height) {
  if (width < 0 || height < 0) {
    return 'You need positive integers to calculate area!';
  }
  return width * height;
}
```

If an argument for width or height is less than 0, then rectangleArea() will return 'You need positive integers to calculate area!'. The second return statement — width * height — will not run.

<br>

# Helper Functions

We can use the return value of a function inside another function. This is called a *helper function*.

```JS
function multiplyByNineFifths(number) {
  return number * (9/5);
};

function getFahrenheit(celsius) {
  return multiplyByNineFifths(celsius) + 32;
};

getFahrenheit(15); // Returns 59
```

*  getFahrenheit() calls multiplyByNineFifths() and passes 15 as an argument.
* multiplyByNineFifths() takes 15 and multiplies it by (9/5), which evaluates to 27 which is then returned to getFahrenheit()
* getFahrenheit() continues to execute adding 32 to 27
* finally the result, 59 is returned to the function call.

Writing helper functions can help break large and difficult tasks into smaller and more manageable ones.

<br>

# Function Expressions

To define a function inside an expression, we can use the function keyword. In a function expression, the function name is usually omitted. A function with no name is called an *anonymous function*. A function expression is often stored in a variable in order to refer to it.

<img src='/JavaScript/JavaScript Syntax/Resources/function_expressions.svg>

To declare a function expression:

* Declare a variable which will also act as the function's name. It's common to use const for this.
* Assign that variable an anonymous *function* then set the function body.

To invoke the expression simply write the name of the var and pass the arguments.
Example: myVariable(argument1, argument2)

Function expressions are ***not*** hoisted.

<br>

# Arrow Functions

A shorter way to write functions by using the "fat arrow" ***() =>*** notation.
This removes the need for the *function* keyword and it goes **AFTER** the ().

```JS
const rectangleArea = (width, height) => {
  let area = width * height;
  return area;
};
```
<br>

# Concise Body Arrow Functions

The most condensed form of the function is known as concise body.


1. Functions that take only a single parameter do not need that parameter to be enclosed in parentheses. However, if a function takes zero or multiple parameters, parentheses are required.

<img src='/JavaScript/JavaScript Syntax/Resources/parameters.svg>

1. A function body composed of a single-line block does not need curly braces. Without the curly braces, whatever that line evaluates will be automatically returned. The contents of the block should immediately follow the arrow =>, and the return keyword can be removed. This is referred to as ***implicit return***.

<img src='/JavaScript/JavaScript Syntax/Resources/return.svg>
