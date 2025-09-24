
A conditional statement checks a specific condition(s) and performs a task based on the condition(s).
<br>

# If Statement

```JS
if (true) {
  console.log('This message will print!'); 
}
// Prints: This message will print!
```

The if keyword followed by a set of parentheses () which is followed by a code block, or block statement, indicated by a set of curly braces {}.
Inside the parentheses (), a condition is provided that evaluates to true or false.
If the condition evaluates to true, the code inside the curly braces {} runs, or executes.
If the condition evaluates to false, the block won’t execute.

<br>

# If... Else Statements

```JS
if (false) {
  console.log('The code in this block will not run.');
} else {
  console.log('But the code in this block will!');
}

// Prints: But the code in this block will!
```

Adding an *else* statement runs the code within it if the condition returns as false.

An else statement must be paired with an if statement, and together they are referred to as an if...else statement.
<br>

# Comparison Operators

Think of comparison statements as questions. When the answer is “yes”, the statement evaluates to true, and when the answer is “no”, the statement evaluates to false.

### Handy comparison operators and their syntax:

* less than: <
* greater than: >
* less than or equal to: <=
* greater than or equal to: >=
* is equal to: ===
* is not equal to: !==

All comparison statements evaluate to either true or false and are made up of:

Two values that will be compared
An operator that separates the values and compares them accordingly (>, <, <=,>=,===,!==)

<br>

# Logical Operators

We can use logical operators to add more sophisticated logic to our conditionals. There are three logical operators:

the ***and*** operator (&&) - checks if multiple specified conditions are met.
the ***or*** operator (||) - check if one of the specified conditions is met.
the ***not*** operator, otherwise known as the bang operator (!) - reverses the value of a boolean. so true becomes false and false becomes true. Example below:

```JS
let excited = true;
console.log(!excited); // Prints false

let sleepy = false;
console.log(!sleepy); // Prints true
```

# Truthy and Falsy

True and False but when we're not checking the specific value.

For example, if we just want to check if a variable exists:

```JS
let myVariable = 'I Exist!';

if (myVariable) {
   console.log(myVariable)
} else {
   console.log('The variable does not exist.')
}
```

The if statement will run because the myVariable has a ***truthy*** value; even though the value of myVariable is not explicitly the value *true*, when used in a boolean or conditional context, it evaluates to true.

### The list of ***falsy*** values includes:

* 0
* empty strings like "" or ''
* null, which represents when there is no value at all
undefined, which represents when a declared variable * lacks a value
* NaN, or Not a Number

```JSS
let numberOfApples = 0;

if (numberOfApples){
   console.log('Let us eat apples!');
} else {
   console.log('No apples left!');
}

// Prints 'No apples left!'
```

# Truthy and Falsy Assignment

In a boolean condition, JavaScript assigns the truthy value to a variable if you use the || operator in your assignment.

For example the following code:

```JS
let username = '';
let defaultName;

if (username) {
  defaultName = username;
} else {
  defaultName = 'Stranger';
}

console.log(defaultName); // Prints: Stranger
```
<br>

Can be written like this:

```JS
let username = '';
let defaultName = username || 'Stranger';

console.log(defaultName); // Prints: Stranger
```
<br>

Because || checks the left-hand condition first, the variable defaultName will be assigned the actual value of username if it is truthy, and it will be assigned the value of 'Stranger' if username is falsy. 
This concept is also referred to as short-circuit evaluation.

# Ternary Operator

```JS
isNightTime ? console.log('Turn on the lights!') : console.log('Turn off the lights!');
```

In the example above:

* The condition, isNightTime, is provided before the ?.
* Two expressions follow the ? and are separated by a colon :.
* If the condition evaluates to true, the first expression executes.
* If the condition evaluates to false, the second expression executes.

Like the if...else statements the ternary operators can be used for conditions that evaluate to true or false.

# Else If Statements

if else if else - it's basically the same as in python just a slight difference in the syntax.

The else if statement always comes after the if statement and before the else statement.

```JS
let stopLight = 'yellow';

if (stopLight === 'red') {
  console.log('Stop!');
} else if (stopLight === 'yellow') {
  console.log('Slow down.');
} else if (stopLight === 'green') {
  console.log('Go!');
} else {
  console.log('Caution, unknown!');
}
```

if/else if/else statements are read from top to bottom, so the first condition that evaluates to true from the top to bottom is the block that gets executed.

# switch keyword

A switch statement provides an alternative syntax that is easier to read and write. A switch statement looks like this:

```JS
let groceryItem = 'papaya';

switch (groceryItem) {
  case 'tomato':
    console.log('Tomatoes are $0.49');
    break;
  case 'lime':
    console.log('Limes are $1.49');
    break;
  case 'papaya':
    console.log('Papayas are $1.29');
    break;
  default:
    console.log('Invalid item');
    break;
}

// Prints 'Papayas are $1.29'
```

* The switch keyword initiates the statement and is followed by ( ... ), which contains the value that each case will compare. In the example, the value or expression of the switch statement is groceryItem.
* Inside the block, { ... }, there are multiple cases. The case keyword checks if the expression matches the specified value that comes after it. The value following the first case is 'tomato'. If the value of groceryItem equalled 'tomato', the console.log() of that case would run.
* The value of groceryItem is 'papaya', so the third case runs — 'Papayas are $1.29' is logged to the console.
* The break keyword tells the computer to exit the block and not execute any more code or check any other cases inside the code block. Note: Without break keywords, the first matching case will run, but so will every subsequent case, regardless of whether or not it matches—including the default. This behavior is different from if/else conditional statements that execute only one block of code.
* At the end of each switch statement, there is a default statement. If none of the case statements are true, then the code in the default statement will run.


# SUMMARY

* An if statement checks a condition and will execute a task if that condition evaluates to true.
* if...else statements make binary decisions and execute different code blocks based on a provided condition.
* We can add more conditions using else if statements.
* Comparison operators, including <, >, <=, >=, ===, and !== can compare two values.
* The logical and operator, &&, checks if both provided expressions are truthy.
* The logical or operator, ||, checks if either provided expression is truthy.
* The bang operator, !, switches the truthiness and falsiness of a value.
* The ternary operator is shorthand to simplify concise if...else statements.
* A switch statement can be used to simplify the process of writing multiple else if statements. The break keyword stops the remaining cases from being checked and executed in a switch statement.