I decided to put this in a separate file although it's part of the same Introduction module.

# Creating Variables

In programming, a variable is a container for a value. 
Variables also provide a way of labeling data with a descriptive name, so our programs can be understood more clearly by the reader and ourselves.

In short, variables label and store data in memory. There are only a few things we can do with variables:

1. Create a variable with a descriptive name.
1. Store or update information stored in a variable.
1. Reference or “get” information stored in a variable.

It is important to distinguish that variables are **not** values; They *contain* values.

## var

```JS
var myName = 'George';
console.log(myName);
// Output: George
```
- *var* creates/declares a new variable
- *myName* is the variable name. The capitalization is a standard and it's called *camel casing*.In camel casing we group words into one, the first word is lowercase, then every word that follows will have its first letter uppercased.
- *=* is the assignment operator.
- 'George' is the value assigned (=) to the variable (myName)

*Personal Note: This is very similar to Python (at least for now) with some small differences like "var" in this case being needed to declare the variable.*

### There are a few general rules for naming variables:

1. Variable names cannot start with numbers.
1. Variable names are case sensitive, so myName and myname would be different variables. It is bad practice to create two variables that have the same name using different cases.
1. Variable names cannot be the same as keywords.

However, *let* and *const* are the preferred variable keywords by many programmers.

## let

The *let* keyword signals that the variable can be reassigned a different value later on.

```JS
let meal = 'Enchiladas';
console.log(meal); // Output: Enchiladas
meal = 'Burrito';
console.log(meal); // Output: Burrito
```

We can also declare a variable without assigning it a value. In such a case, the variable will be automatically initialized with a value of undefined.

```JS
let price;
console.log(price); // Output: undefined
price = 350;
console.log(price); // Output: 350
```

## const

```JS
const myName = 'Gilberto';
console.log(myName); // Output: Gilberto
```

Unlike var and let, *const* declared variables cannot be reassigned because the value assigned upon declaration is a constant.
This also means that const variables **must** be assigned a value when declared. If we leave it empty we'll get a SyntaxError.

<br> 

# Mathematical Assignment Operators

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators" target="_blank"> Expressions and Operators Doc </a>

```JS
let w = 4;
w = w + 1;

console.log(w); // Output: 5
```

We can use variables and math operators to calculate and assign new values to a variable.
In the above example we declare the variable w with value 4 but then reassign it to it's existing value + 1 which assigns the new value of 5 to the variable.

Another way we could have reassigned w after performing some mathematical operation on it is to use built-in mathematical assignment operators. We could rewrite the code above to be:

```JS
let w = 4;
w += 1;

console.log(w); // Output: 5
```

We also have access to other mathematical assignment operators like -=, *=, and /= — which work in a similar fashion.

```JS
let x = 20;
x -= 5; // Can be written as x = x - 5
console.log(x); // Output: 15

let y = 50;
y *= 2; // Can be written as y = y * 2
console.log(y); // Output: 100

let z = 8;
z /= 2; // Can be written as z = z / 2
console.log(z); // Output: 4
```

## The Increment and Decrement Operator

Other mathematical assignment 
operators include the increment operator (++) and decrement operator (--).

The increment operator will increase the value of the variable by 1. The decrement operator will decrease the value of the variable by 1. 

```JS
let a = 10;
a++;
console.log(a); // Output: 11
let b = 20;
b--;
console.log(b); // Output: 19

```

# String Concatenation with Variables

The + operator can be used to combine two string values, even if those values are being stored in variables.

```JS
let myPet = 'tarantula';
console.log('I own a pet ' + myPet + '.'); 
// Output: 'I own a pet tarantula.'
```

# String Interpolation

We can insert, or *interpolate*, variables into strings using <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals" target="_blank"> template literals</a>.

```JS
const myPet = 'armadillo';
console.log(`I own a pet ${myPet}.`);
// Output: I own a pet armadillo.
```

- A template literal is wrapped by backticks "**`**".
- Inside it we have a placeholder - ${} which contains the *myPet* variable value.
When we interpolate "`I own a pet ${myPet}.`", the output we print is the string: 'I own a pet armadillo.'

Using template literals, we can more easily tell what the new string will be. We also don’t have to worry about escaping double quotes or single quotes.

Another example which helps me understand this better:

```JS
let name = 'George';
let food = 'pizza';

console.log(`My name is ${myName}. My favorite food is ${food}`);
```

# typeof operator

If we need to check the data type of a variable’s value, we can use the typeof operator. It checks the value to its right and returns, or passes back, a string of the data type.

```JS
const unknown1 = 'foo';
console.log(typeof unknown1); // Output: string

const unknown2 = 10;
console.log(typeof unknown2); // Output: number

const unknown3 = true; 
console.log(typeof unknown3); // Output: boolean
```

# SUMMARY

* Variables hold reusable data in a program and associate it with a name.
* Variables are stored in memory.
* The var keyword is used in pre-ES6 versions of JS.
* let is the preferred way to declare a variable when it can be reassigned, and const is the preferred way to declare a variable with a constant value.
* Variables that have not been initialized store the primitive data type undefined.
* Mathematical assignment operators make it easy to calculate a new value and assign it to the same variable.
* The + operator is used to concatenate strings, including string values held in variables.
* In ES6, template literals use backticks ` and ${} to interpolate values into a string.
* The typeof keyword returns the data type (as a string) of a value.