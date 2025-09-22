<br>
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank"> JavaScript Documentation </a>
<br>

# Console

In JavaScript, the console keyword refers to an object, a collection of data and actions, that we can use in our code. 
One action, or method, built into the console object is the .log() method. When we write console.log(), what we put inside the parentheses will get printed, or logged, to the console.

```JS
console.log(5); 
```

Most of JS code will run fine without a ; at the end but it's good practice to still add it so it's not left out by mistake in the few instances where it's required.

# Comments

Comments can explain what the code is doing, leave instructions for developers using the code, or add any other useful annotations.

## Single-line comments

A single-line comment is denoted with //.

```JS
// Single-line comment
```
## Multi-line comments

These are similar to CSS comments and are written with /* */

```JS
/* I like how this course assumes zero programming
    knowledge and teaches the very basics.
*/
``` 

# Data Types

### In JavaScript, there are eight fundamental data types:

* Number: Any number, including numbers with decimals: 4, 8, 1516, 23.42.
* BigInt: Any number, greater than 253-1 or less than -(253-1), with n appended to the number: 1234567890123456n.
* String: Any grouping of characters on the keyboard (letters, numbers, spaces, symbols, etc.) surrounded by single quotes: ' ... ' or double quotes " ... ", though we prefer single quotes. Some people like to think of string as a fancy word for text.
* Boolean: This data type only has two possible values — either true or false (without quotes). It’s helpful to think of booleans as on and off switches or as the answers to a “yes” or “no” question.
* Null: This data type represents the intentional absence of a value, and is represented by the keyword null (without quotes).
* Undefined: This data type is denoted by the keyword undefined (without quotes). It also represents the absence of a value, though it has a different use than null. undefined means that a given value does not exist.
* Symbol: A newer feature of the language, symbols are unique identifiers that are useful in more complex coding. No need to worry about these for now.
* Object: Collections of related data.

The first seven of those types are considered primitive data types. Objects are more complex.

# Arithmetic Operators

```JS
console.log(3+5);
```

An operator is a character that performs a task in our code.
JavaScript has several built-in arithmetic operators. 

### These include:

* Add: +
* Subtract: -
* Multiply: *
* Divide: /
* Remainder: %

The remainder operator, sometimes called modulo, returns the number that remains after the right-hand number divides into the left-hand number as many times as it evenly can

# String Concatenation

```JS
console.log('wo' + 'ah ' + 'mama!'); // Prints 'woah mama!'
```

When a + operator is used on two strings it appends the right string to the left string.This process of appending one string to another is called concatenation.

In the above example there's a space after "ah". This is because if we don't add it the two strings will be joined into one word.


# Properties

```JS
console.log('Hello'.length); // Prints the number of characters - 5
```

All data types have properties associated with them. For example strings have a property of "length".
We can retrieve property information by appending the string with a period and then the property name.

The "." is another operator! It's called the dot operator.

# Methods

Methods are actions we can perform.
Data types have access to specific methods that allow us to handle instances of that data type.
We *call* these methods by appending an instance with:
- dot operator
- the name of the method
- ()

Example: 'example string'.methodName()

When we use console.log(), we’re calling the .log() method on the console object. 

```JS
console.log('hello'.toUpperCase()); // Prints 'HELLO'
console.log('Hey'.startsWith('H')); // Prints true
```
In the above example:

The *.toUpperCase()* method is called on the string instance 'hello'. The result is logged to the console. This converts a string in all capital letters. 'HELLO' is logged in the console as a result.

The *.startsWith()* method is called on the string instance 'Hey'. This method also accepts the character 'H' as an input, or argument, between the parentheses. This method checks whether a string begins with the specified characters. It returns true if it does, otherwise false. Since the string 'Hey' does start with the letter 'H', the method returns the boolean true.

A list of the built-in string methods can be found in the <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String" target="_blank"> JS Documentation </a>

# Built-in Objects

There are quite a few <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects" target="_blank"> Built-in Objects </a> besides console.
Building custom objects will be explored later.


## Math Object

To perform some more complex operations JS has the built-in Math object. As previously mentioned objects come with methods.

```JS
console.log(Math.floor(Math.random() * 50)); // Prints a random whole number between 0 and 50
```

In the above example the end goal is to generate a random whole number between 0 - 50 and then print it in the console. Let's break it down:
1. First, we call the *.random()* method on the *Math* object which generates a random number between 0 and 1. 
2. In order for us to get a number between 0 and 50 we multiply the output of *Math.random()* by 50 using the "*" operator. However, the output by default is a decimal.
3. To solve this we can call the *.floor()* method on the *Math* object which will take the decimal output of *.random()* and round it down to the nearest whole number.
4. Finally, we call *.log()* on *console* so we can print the output in the console.

```
Math.random() make random number but number only 1 or 0. 
Multiply by 50 to get random number 0-50. 
Now number not whole.
Wrap it in Math.floor() to smash number down so it's whole. 
Now wrap all that in console.log() to show number in console.
```
<img src="https://i.giphy.com/eJLXXjN1ZGS4g.webp" width= 300px height = auto>

<br>
<br>

The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math" target="_blank"> Math Documentation </a> has all properties and methods on the Math object.

<br>

# SUMMARY

- Data is printed, or logged, to the console, a panel that displays messages, with console.log().
- We can write single-line comments with // and multi-line comments between /* and */.
- There are eight fundamental data types in JavaScript: numbers, BigInts, strings, booleans, null, undefined, symbols, and 
objects
- Numbers are any number without quotes. For example: 23.8879
- Strings are characters wrapped in single or double quotes. For example: 'Sample String'
- The built-in arithmetic operators include +, -, *, /, and %.
- Objects, including instances of data types, can have properties that store information. The properties are denoted with a . after the name of the object, for example: 'Hello'.length.
- Objects, including instances of data types, can have methods that perform actions. Methods are called by appending the object or instance with a period, the method name, and parentheses. For example: 'hello'.toUpperCase().
- We can access properties and methods by using the . (dot operator).
- Built-in objects, including Math, are collections of methods and properties that JavaScript provides.

## BONUS RESOURCES: <a href="https://www.codecademy.com/resources/docs/javascript"> Codecademy JS Docs </a> ; <a href="https://www.codecademy.com/workspaces/new"> Codecademy Workspaces </a>
