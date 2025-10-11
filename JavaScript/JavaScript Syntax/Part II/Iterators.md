
# Higher Order Functions

A higher-order function is a function that either accepts functions as parameters, returns a function, or both!

<br>

## Functions as Data

<br>

We can assign functions to variables, and we can reassign them to new variables.
For example, if we have a function with a really long name, we can just reassign it to a variable with a shorter name to keep the codebase neat and easy to read.

Example:

```JS
const announceThatIAmDoingImportantWork = () => {
    console.log("I’m doing very important work!");
};

// now let's reassign the function

const busy = announceThatIAmDoingImportantWork;

busy(); // This function call barely takes any space!
```

We ommit the () when reassigning so that we can assign the function itself to the busy variable instead of the function output.

<br>

## Functions as Parameters

Functions can take other functions as parameters.We call functions that get passed in as parameters callback functions. Callback functions get invoked during the execution of the higher-order function.

With callback functions, we pass in the function itself by typing the function name without the parentheses.

```JS
const higherOrderFunc = param => {
  param();
  return `I just invoked ${param.name} as a callback function!`
}
 
const anotherFunc = () => {
  return 'I\'m being invoked by the higher-order function!';
}

higherOrderFunc(anotherFunc);
```

We wrote a higher-order function higherOrderFunc that accepts a single parameter, param. Inside the body, param gets invoked using parentheses. And finally, a string is returned, telling us the name of the callback function that was passed in.

<br>

# Iterators

The built-in JavaScript array methods that help us iterate are called iteration methods, at times referred to as iterators.

<br>

## The .forEach() Method

Aptly named, .forEach() will execute the same code for each element of an array.

<img src='./Resources/iterator anatomy.svg'>

### Breakdown of the above example:

* groceries.forEach() calls the forEach method on the groceries array.
* .forEach() takes a callback function as an argument. 
* .forEach() loops through the array and executes the callback function for each element. During each execution, the current element is passed as the argument for the callback function.
* The return value for .forEach() will always be undefined.

Another way to pass a callback for .forEach() is to use the arrow function syntax.
```JS
groceries.forEach(groceryItem => console.log(groceryItem));
```

I prefer this as it's a lot simpler and less code.

<br>

## The .map() Method

When it's called on an array, it takes an argument of a callback function and returns a new array.

For example:

```JS
const numbers = [1, 2, 3, 4, 5]; 

const bigNumbers = numbers.map(number => {
  return number * 10;
});
```

by using .map() we take each number from the numbers array, multiply it by 10 and store it in a new array called bigNumbers. So the output of bigNumbers would be 10, 20, 30, 40, 50.

<br>

## The .filter() Method

Like the .map() this method also returns a new array. However, as the name suggests this filters some elements out of the original array.

<img src='./Resources/wow.jpg'>

Example:

```JS
const words = ['chair', 'music', 'pillow', 'brick', 'pen', 'door']; 

const shortWords = words.filter(word => {
  return word.length < 6;
});
```
### Breakdown:

* words is an array that contains string elements.
* const shortWords = declares a new variable that will store the returned array from invoking .filter().
* The callback function is an arrow function that takes a single parameter, word. Each element in the words array will be passed to this function as an argument.
* word.length < 6; is the condition in the callback function. Any word from the words array that has fewer than 6 characters will be added to the shortWords array.

<br>

## The .findIndex() Method

This one lets us find the location of an element in an array. It also outputs into a new array.

Here's an example:

```JS
const jumbledNums = [123, 25, 78, 5, 9]; 

const lessThanTen = jumbledNums.findIndex(num => {
  return num < 10;
});
```

### and ofc here's the breakdown of the example:

* jumbledNums is an array that contains elements that are numbers.
* const lessThanTen = declares a new variable that stores the returned index number from invoking .findIndex().
* The callback function is an arrow function that has a single parameter, num. Each element in the jumbledNums array will be passed to this function as an argument.
* num < 10; is the condition that elements are checked against. .findIndex() will return the index of the first element that evaluates to true for that condition.

Very similar to previously discussed methods.

If there isn’t a single element in the array that satisfies the condition in the callback, then .findIndex() will return -1.

<br>

## The .reduce() Method

This one is a bit different. It reduces the original array but outputs a single value.

