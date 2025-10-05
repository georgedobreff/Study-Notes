Loops are blocks of code that repeat a set of instructions until a specified condition, called the *stopping condition* is reached.

When we have a process that needs to repeat multiple times in a row we write a loop.

<br>

# The For Loop

The typical for loop includes an iterator variable that usually appears in all three expressions. The iterator variable is initialized, checked against the stopping condition, and assigned a new value on each loop iteration. 


### A for loop contains three expressions separated by ";" inside the parentheses:
<br>

1. an initialization starts the loop and can also be used to declare the iterator variable.
1. a stopping condition is the condition that the iterator variable is evaluated against — if the condition evaluates to true, the code block will run. If it evaluates to false, the code will stop.
1. an iteration statement is used to update the iterator variable on each loop.
<br>

```JS
for (let counter = 0; counter < 4; counter++) {
  console.log(counter);
}
```
<br>


### Let’s break down the code example:

* The initialization is *let counter = 0*, so the loop will start counting at 0.
* The stopping condition is *counter < 4*, meaning the loop will run as long as the iterator variable, *counter*, is less than 4.
* The iteration statement is *counter++*. This means after each loop, the value of counter will increase by 1. For the first iteration, counter will equal 0. For the second iteration, it will equal 1, and so on.
* The code block within the curly braces, *console.log(counter)*, will continue to execute until the condition evaluates to *false*. The condition will be false when *counter* is greater than or equal to 4 — the point that the condition becomes false is sometimes called the *stop condition*.

When writing/changing loops, there is a chance we will get a dreaded infinite loop, which essentially stops our programming from running anything else! This occurs when the loop’s stopping condition is never met, causing the loop to continue iterating, blocking the rest of the program from executing.

<br>

### If we want to run a backwards loop we can:

* Set the iterator variable to the highest desired value in the initialization expression.
* Set the stopping condition for when the iterator variable is less than the lowest desired amount.
* The iterator should decrease in intervals after each iteration.

Example:

```JS
for (let counter = 3; counter >= 0; counter--){
  console.log(counter);
}
```
<br>

# Looping through Arrays

We can use a for loop to perform the same operation on each element on an array.

To loop through each element in an array, a for loop should use the array’s *.length* property in its condition.

```JS
const animals = ['Grizzly Bear', 'Sloth', 'Sea Lion'];
for (let i = 0; i < animals.length; i++){
  console.log(animals[i]);
}
```

In the loop above, we’ve named the iterator variable i. This is a variable naming convention used a lot in loops. 

When we use i to iterate through arrays we can think of it as being short-hand for the word index.

We set the stopping condition to the *.length* of the animals array.

<br>

# Nested Loops

When one loop is running inside another loop, we call that a nested loop. 

```JS
const arrayA = [6, 19, 20];
const arrayB = [19, 81, 2];
for (let i = 0; i < arrayA.length; i++) {
  for (let j = 0; j < arrayB.length; j++) {
    if (arrayA[i] === arrayB[j]) {
      console.log('Both arrays have the number: ' + arrayB[j]);
    }
  }
}
```

### What's happening in the above example:

For each element in the outer loop array, arrayA, the inner loop will run in its entirety comparing the current element from the outer array, arrayA[i], to each element in the inner array, arrayB[j]. When it finds a match, it prints a string to the console.

The below is an example of comparing two arrays with a nested loop and pushing matching values to a third array.

```JS
const bobsFollowers = ['John Pork', 'Mike Hunt', 'Hugh Janus', 'Tony'];

const tinasFollowers = ['Samuel', 'Mike Hunt', 'Hugh Janus'];

const mutualFollowers = [];

for (let a = 0; a < bobsFollowers.length; a++){
  for(let b = 0; b < tinasFollowers.length; b++){
    if (bobsFollowers[a] === tinasFollowers[b]){
      mutualFollowers.push(tinasFollowers[b])
    }
  }
}
console.log(mutualFollowers)
```
<br>

# The While Loop

```JS
// A while loop that prints 1, 2, and 3
let counterTwo = 1;
while (counterTwo < 4) {
  console.log(counterTwo);
  counterTwo++;
}
```

### Let's break this down: 

The *counterTwo* variable is declared before the loop. Since it’s in the global scope, we can access it inside our while loop.

* We start our loop with the keyword while followed by our stopping condition, or test condition. This will be evaluated before each round of the loop. While the condition evaluates to true, the block will continue to run. Once it evaluates to false the loop will stop.
* Next, we have our loop’s code block, which prints counterTwo to the console and increments counterTwo.

If we didn’t increment counterTwo inside the block, counterTwo would always have its initial value, 1. That would mean the testing condition counterTwo < 4 would always evaluate to true and our loop would never stop running!

A while loop is ideal when we don’t know in advance how many times the loop should run. 

<br>

# Do...While Statements

In some cases, we want a piece of code to run at least once and then loop based on a specific condition after its initial run. This is where the do...while statement comes in.

This statement says to do a task once and then keep doing it until a specified condition is no longer met.

```JS
let countString = '';
let i = 0;

do {
  countString = countString + i;
  i++;
} while (i < 5);

console.log(countString);
```

In this example, the code block makes changes to the countString variable by appending the string form of the i variable to it. First, the code block after the do keyword is executed once. Then the condition is evaluated. If the condition evaluates to true, the block will execute again. The looping stops when the condition evaluates to false.

while and do...while loops are different! Unlike the while loop, do...while will run at least once, whether or not the condition evaluates to true.

```JS
const firstMessage = 'I will print!';
const secondMessage = 'I will not print!'; 

// A do while with a stopping condition that evaluates to false
do {
 console.log(firstMessage)
} while (true === false);

// A while loop with a stopping condition that evaluates to false
while (true === false){
  console.log(secondMessage)
};
```

# The break Keyword

It allows programs to “break” out of the loop from within the loop’s block.

```JS
for (let i = 0; i < 99; i++) {
  if (i > 2 ) {
     break;
  }
  console.log('Banana.');
}

console.log('Orange you glad I broke out the loop!');
```
With breaks, we can add test conditions besides the stopping condition, and exit the loop when they’re met.


# for...of loop

```JS
const hobbies = ['singing', 'eating', 'quidditch', 'writing'];
 
for (const hobby of hobbies) {
  console.log(`I enjoy ${hobby}.`);
}
```

for loops are great but the above is a more efficient way to achieve the same. instead of 
```JS
for (let i = 0; i < hobbies.length; i++) 
```
we just do
```JS
for (const hobby of hobbies)
```
hobby indicates each item in the array hobbies.

This loop is not a replacement for the "for" loop, however when we simply need to iterate through all items in an array it comes in handy as its syntax is simpler.
