Arrays are basically lists. They can store any data type and like lists they are ***ordered***, meaning each item has a numbered position.

```JS
let newYearsResolutions = ['Keep a journal', 'Take a falconry class', 'Learn to juggle'];
```
<br>

# Creating an Array

One way we can create an array is to use an **array literal**. An array literal creates an array by wrapping items in square brackets [].

<img src='./Resources/arrays.svg'>

### Let’s take a closer look at this array example:

* The array is represented by the square brackets [] and the content inside.
* Each content item inside an array is called an **element**.
* Each element is separated by a comma.
* There are three different elements inside the array.
* Each element inside the array is a different data type.

We can also save an array to a variable like in the first code example above.

<br>

# Accessing Elements

The position of each element in an array is called an **index**. The starting position is always 0.

<img src='./Resources/arrays_index.svg'>

<br>

### In the code snippet above:

* cities is an array that has three elements: 'New York', 'Beijing', and 'Nairobi'.
* We’re using bracket notation, [], with the index after the name of the array to access the element.
* cities[0] will access the element at index 0 in the array cities. We can think of cities[0] as accessing the space in memory that holds the string 'New York'.

We can also access individual characters in a string using bracket notation and the index. 
For example: 

```JS
const hello = 'Hello World';
console.log(hello[6]);
// Output: W
```

Individual elements from an array can also be stored in variables.

For example if we want to pull New York from the array above and store it in a variable we can do:

```JS
usCity = cities[0];
```

If we try to access and index that does not contain an element we get 'undefined' as output.

<br>

# Update Elements

We can also update the values of elements. For example:

```JS
let seasons = ['Winter', 'Spring', 'Summer', 'Fall'];

seasons[3] = 'Autumn';
console.log(seasons); 
//Output: ['Winter', 'Spring', 'Summer', 'Autumn']
```

<br>

# Arrays with let and const

Elements in an array declared with const remain **mutable** meaning we can change the elements inside the array but can't reassign a new array or value. For example if we declare the array with const array1 we can't change array1 to array2 but we can change the elements inside array1

<br>

# The .length property

```JS
const newYearsResolutions = ['Keep a journal', 'Take a falconry class'];

console.log(newYearsResolutions.length);
// Output: 2
```

One of an array’s built-in properties is length, and it returns the number of items in the array.


### In the example above, we log newYearsResolutions.length to the console:

* We use dot notation, chaining a period with the property name to the array, to access the length property of the newYearsResolutions array.
* Then, we log the length of newYearsResolutions to the console.
* Since newYearsResolutions has two elements, 2 would be logged to the console.

<br>

# .push() Method

This allows us to add more items to an existing array which go at the end of the array.

```JS
const itemTracker = ['item 0', 'item 1', 'item 2'];

itemTracker.push('item 3', 'item 4');

console.log(itemTracker); 
// Output: ['item 0', 'item 1', 'item 2', 'item 3', 'item 4'];
```

<br>

### How it works:

* We access the push() method by using the dot notation and connect it to the itemTracker.
* Then we call it like a function (because it is one).
* .push() can take a single or multiple arguments separated by commas. In this example we add item 3 and item 4.
* This ***mutates*** the array and it is sometimes called a **destructive** array method as it changes the initial array.

<br>

# .pop() Method

It removes the last element in an array. 

```JS
const newItemTracker = ['item 0', 'item 1', 'item 2'];

const removed = newItemTracker.pop();

console.log(newItemTracker); 
// Output: [ 'item 0', 'item 1' ]
console.log(removed);
// Output: item 2
```
<br>

### Breakdown of the above example:

* Calling .pop() on the newItemTracker array removed 'item 2' from the end.
* .pop() does not take any arguments — it simply removes the last element of newItemTracker.
* .pop() returns the value of the last element. In the example, we store the returned value in a variable removed to be used later.
* .pop() is a method that mutates the initial array.

<br>

# List of Array Methods
 

* .at() - Returns the element at a specified index in an array.

* .concat() - Merges, or concatenates, two or more arrays.

* .copyWithin() - Returns a mutated array with part of it copied to another location in the same array, and its length unchanged.

* .entries() - Returns an iterator with key/value pairs for each index in the array.

* .every() - Checks if all elements in an array satisfy the condition specified by the given function.

* .fill() - Changes all elements within a range of indices in an array to a static value.

* .filter() - Creates a new array containing the elements from the original array that pass a test implemented by a provided function.

* .find() - Returns the first element in the array that satisfies the given function.

* .findIndex() - Returns the first index that passes the callback function's test. Returns -1 if no element passes the test.

* .findLast() - Returns the last instance of an element in an array that meets the specified condition.

* .findLastIndex() - Iterates through the array in reverse order and returns the index that passes the provided testing function.

* .flatMap() - Returns a new array formed by applying a callback function to each element of the original array, then flattening the result by one level.

* .forEach() - Loops over a given array, passing each item in the array into the callback function provided.

* .from() - Creates a new Array instance from an iterable or array-like object.

* .includes() - Returns true if a given value is included in an array.

* .indexOf() - Returns the first index at which a specified element can be found in an array, or -1 if not present.

* .isArray() - Returns true for arrays, otherwise false.

* .join() - Elements of an array are converted to strings and concatenated together, returning the resulting string.

* .keys() - Returns a new array iterator object containing the keys for each index in the array.

* .lastIndexOf()- Returns the last index at which an element can be found.

* .length - Returns the specific number of elements in the array.

* .map() - Creates a new array with the results of calling a function for every element in array.

* .pop() - Removes the last element of an array, decrements the array length, and returns the value that it removed.

* .push() - Adds one or more elements to the end of the array and returns the new length.

* .reduce() - Executes a reducer function on each element of an array, resulting in a single output value.

* .reverse() - Reverses the order of the elements of an array in place and returns the reversed array.

* .shift() - Removes and returns the first element of the array. All subsequent elements will shift down one place.

* .slice() - Returns a shallow copy of a part of an array. It contains references to the sliced elements in the original array, not the elements themselves.

* .some() - Runs a conditional through an array and returns a boolean if any value fulfills the conditional.

* .sort() - Sorts the elements of an array in place.

* .splice() - Modifies an array by inserting, deleting, and/or replacing array elements then returns an array of deleted elements.

* .toLocaleString() - Converts array elements to localized string representations and joins them with locale-specific separators.

* .toReversed() - Reverses the elements within the array and returns a new copy of the array.

* .toSorted() - Takes an array and returns a new array with all the elements sorted in ascending order.

* .toSpliced() - Returns a new array with deleted, replaced, or inserted values at the given index.

* .toString() - Returns a string with each of the array values, separated by commas. Does not mutate the original array.

* .unshift() - Adds one or more elements to beginning of array and returns new length.

* .valueOf() - Returns the value of all the elements of the original array.

* .values() - Returns a new array iterator object that contains the values of each element in the array.

* .with() - Returns a copy of an array with the given modification.

* flat() - Creates a new array with all sub-array elements recursively concatenated into it up to the specified depth.

* reduceRight() - Applies a reducer function to array elements from right to left, accumulating a single output value.

*Making this list was not fun. I hope I find it useful.*

<br>

# Arrays and Functions

```JS
const flowers = ['peony', 'daffodil', 'marigold'];

function addFlower(arr) {
  arr.push('lily');
}

addFlower(flowers);

console.log(flowers); // Output: ['peony', 'daffodil', 'marigold', 'lily']
```

When we pass an array into a function, if the array is mutated inside the function, that change will be maintained outside the function as well. This concept is also sometimes called **pass-by-reference**, since what we’re actually passing to the function is a reference to where the variable is stored in memory and changing the data there.

### Example breakdown: 

* The flowers array starts with three elements.
* The function addFlower() has a parameter of arr and uses .push() to add a 'lily' element into arr.
* We call addFlower() with an argument of flowers, which will execute the code inside addFlower.
* We check the value of flowers and it now includes the 'lily' element! The array was mutated!

<br>

# Nested Arrays

```JS
const nestedArr = [[1], [2, 3]];
```

When an array contains another array, it is known as a nested array.

We can access nested arrays the same way, however if we want to access elements inside the nested array we can do that by ***chaining*** the brackets. Example:

```JS
const nestedArr = [[1], [2, 3]];

console.log(nestedArr[1]); // Accesses the nested array itself. Output: [2, 3]
console.log(nestedArr[1][0]); // Accesses the element with index 0 inside the nested array. Output: 2
```

<br>
<br>

# SUMMARY

* Arrays are lists that store data in JavaScript.
* Arrays are created with brackets [].
* Each item within an array is located at a numbered position, or index, starting at 0.
* We can access one item in an array using its index, with syntax like: myArray[0].
* We can also change an item in an array using its index, with syntax like myArray[0] = 'new string';
* Arrays have a .length property, which allows you to see how many items are in an array.
* Arrays have their own methods, including .push() and .pop(), which add and remove items from an array, respectively.
* Arrays have many methods that perform different tasks, such as .slice() and 
.shift(). You can find documentation at the Mozilla Developer Network website.
* Some built-in methods are mutating, meaning the method will change the array, while others are not mutating. You can always check the documentation.
* Variables that contain arrays can be declared with let or const. Even when declared with const, arrays are still mutable. However, a variable declared with const cannot be reassigned.
* Arrays mutated within a function will keep that change even outside the function.
* Arrays can be nested inside other arrays.
* To access elements in nested arrays, chain indices using bracket notation.
