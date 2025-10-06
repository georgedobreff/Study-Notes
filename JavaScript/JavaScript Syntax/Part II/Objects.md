At their core, JavaScript objects are containers storing related data and functionality, but that deceptively simple task is extremely powerful in practice. 
<br>

# Creating Objects

Objects can be assigned to variables and we use {} to designate an *object literal*.

We fill an object with data that's organized into **key-value** pairs. We call these **properties**.

A key's value can be anything, including functions or even other objects.

```JS
// An object literal with two properties
let vehicle1 = {
 /* key */ 'Fuel Type': 'diesel'/* value */,
 /* key */ color: 'silver' /* value */
};
```

The Fuel Type key in the above example has '' because it contains a space. We could write it as fuelType and '' won't be needed.

<br>

# Accessing Properties

There are two ways to do this. First one is the dot notation.

## Dot Notation (.)

With property dot notation, we write the object’s name, followed by the dot operator, and then the property name (key):
```JS
let spaceship = {
  homePlanet: 'Earth',
  color: 'silver'
};
spaceship.homePlanet; // Returns 'Earth'
spaceship.color; // Returns 'silver'
```

If we try access a property on that object that doesn't exist the output will be *undefined*.


## Bracket Notation []

The second way to access a key's value is with brackes []

To use bracket notation to access an object’s property, we pass in the property name (key) inside square brackets as a string.

We **must** use bracket notation when accessing keys that are not valid identifier names (e.g., keys that begin with a number or contain spaces or special characters). Without bracket notation in these situations, our code would throw an error.

```JS
let spaceship = {
  'Fuel Type': 'Turbo Fuel',
  'Active Duty': true,
  homePlanet: 'Earth',
  numCrew: 5
};
spaceship['Active Duty'];   // Returns true
spaceship['Fuel Type'];   // Returns 'Turbo Fuel'
spaceship['numCrew'];   // Returns 5
spaceship['!!!!!!!!!!!!!!!'];   // Returns undefined
```

We can also use a variable inside the brackets to select the keys of an object which can be helpful when working with functions.

```JS
let returnAnyProp = (objectName, propName) => objectName[propName];
 
returnAnyProp(spaceship, 'homePlanet'); // Returns 'Earth'
```

If we tried to write our returnAnyProp() function with dot notation (objectName.propName), the computer would look for a key of 'propName' on our object and not the value of the propName parameter.

<br>

# Property Assignment

Objects are mutable so we can assign new key-value pairs utilizing either the dot or brackets notation along with the *(=)* operator.



### One of two things can happen with property assignment:

* If the property already exists on the object, whatever value it held before will be replaced with the newly assigned value.
* If there was no property with that name, a new property will be added to the object.

Similar to arrays we can't reassign an object declared with *const* but we can mutate its properties.

```JS
const spaceship = {type: 'shuttle'};
spaceship = {type: 'alien'}; // TypeError: Assignment to constant variable.
spaceship.type = 'alien'; // Changes the value of the type property
spaceship.speed = 'Mach 5'; // Creates a new key of 'speed' with a value of 'Mach 5'
```

We can also *delete* a property with the **delete** operator.

```JS
delete spaceship.speed;
```
<br>

# Methods 

When the data stored in an object is a function it's called a *method*.

We can include methods in our object literals by creating ordinary, colon-separated key-value pairs. The key serves as our method’s name, while the value is an anonymous function expression.
With the new method syntax introduced in ES6, we can omit the colon and the function keyword.

```JS
const bestMovies = {
  scifi() { 
    console.log('Star Wars is one of the best Sci-Fi movies!')
  },
  action() {
    console.log('John Wick')
  }
};

bestMovies.scifi(); // Prints Star Wars is one of the best Sci-Fi movies!
```
<br>

# Nested Objects

In production an object might have another object as a property, which in turn could have a property that’s an array of even more objects!

Example:
```JS
const spaceship = {
  telescope: {
    yearBuilt: 2018,
    model: '91031-XLT',
    focalLength: 2032 
  },
  crew: {
    captain: { 
      name: 'Sandra', 
      degree: 'Computer Engineering', 
      encourageTeam() { console.log('We got this!') } 
    }
  },
  engine: {
    model: 'Nimbus2000'
  },
  nanoelectronics: {
    computer: {
      terabytes: 100,
      monitors: 'HD'
    },
    'back-up': {
      battery: 'Lithium',
      terabytes: 50
    }
  }
}; 
```

We can chain operators to access nested properties. 

```JS
spaceship.nanoelectronics['back-up'].battery; // Returns 'Lithium'
```

### In the above example:

* First, the computer evaluates spaceship.nanoelectronics, which results in an object containing the back-up and computer objects.
* We accessed the back-up object by appending ['back-up'].
* The back-up object has a battery property, accessed with .battery, which returned the value stored there: 'Lithium'

<br>

# Pass By Reference

This means when we pass a variable assigned to an object into a function as its argument, the code interprets the parameter name as a pointer (to the space in memory holding that object). As a result, functions that change object properties mutate the object permanently, even if the object is assigned to a const variable.

Example:

```JS
const spaceship = {
  homePlanet : 'Earth',
  color : 'silver'
};
 
let paintIt = obj => {
  obj.color = 'glorious gold'
};
 
paintIt(spaceship);
 
spaceship.color // Returns 'glorious gold'
 ```

 The function paintIt() permanently changed the color of our spaceship object.

 Here is the practice example from the lesson:
 
 ```JS
 let spaceship = {
  'Fuel Type' : 'Turbo Fuel',
  homePlanet : 'Earth'
};

// Write your code below
let greenEnergy = obj => {
  obj['Fuel Type'] = 'avocado oil';
}

let remotelyDisable = obj => {
  obj.disabled = true;
}

greenEnergy(spaceship)
remotelyDisable(spaceship)
console.log(spaceship)
```
<br>

# Looping through Objects

Since objects are not ordered like arrays we have to use ***for...in*** which will execute a given block of code for each property in an object.

```JS
// for...in
for (let crewMember in spaceship.crew) {
  console.log(`${crewMember}: ${spaceship.crew[crewMember].name}`);
}
```

for...in will iterate through each property of the spaceship.crew object. In each iteration, the variable crewMember is set to one of spaceship.crew object’s keys, enabling us to log a list of crew members’ role and name.

here's a more generic example to illustrate what each piece is:

```JS
for (let variableName in outerObject.innerObject) {
  console.log(`${variableName}: ${outerObject.innerObject[variableName].propertyName}`)
};
```

<br>
<br>

# SUMMARY

* Objects store collections of key-value pairs.
* Each key-value pair is a property — when a property is a function, it is known as a method.
* An object literal is composed of comma-separated key-value pairs surrounded by curly braces.
* We can access, add, or edit a property within an object by using dot notation or bracket notation.
* We can use methods to our object literals using key-value syntax with anonymous function expressions as values or by using the new ES6 method syntax.
* We can navigate complex, nested objects by chaining operators
* Objects are mutable — we can change their properties even when they’re declared with const.
* Objects are passed by reference — when we make changes to an object passed into a function, those changes are permanent.
* We can iterate through objects using the for...in syntax.


<br>
<br>

# ADVANCED OBJECTS

## The this keyword

The this keyword references the calling object, which provides access to the calling object’s properties. By default JS doesn't have access to the object's properties.

```JS
const goat = {
  dietType: 'herbivore',
  diet() {
    console.log(this.dietType);
  }
};

goat.diet(); 
// Output: herbivore
```

if we don't add "this" before dietType in the console.log we'll get "ReferenceError: dietType is not defined".

<br>

## Arrow functions & the this keyword

Arrow functions inherently bind, or tie, an already defined "this" value to the function itself that is NOT the calling object but one in the global scope.
If we use the "this" keyword then we should not use the arrow functions.

<br>

## Privacy

Privacy in objects refers to the idea that certain properties should **not** be mutable.
Some languages have this built-in, however JS doesn't. A common practice is to simply put an underscore before the name of a property to indicate that it shouldn't be altered.
Example:
```JS
const bankAccount = {
  _amount: 1000
}
```

While adding an underscore doesn't block us from modifying the property it signals to anyone reading the code that it's not a good idea to change it.

<br>

## Getters

These are methods that get and return the internal properties of an object but they can do more.

```JS
const person = {
  _firstName: 'George',
  _lastName: 'Dobreff',
  get fullName() {
    if (this._firstName && this._lastName){
      return `${this._firstName} ${this._lastName}`;
    } else {
      return 'Missing a first name or a last name.';
    }
  }
}

// To call the getter method: 
person.fullName; // 'George Dobreff'
```

### In the getter method above:

* We use the *get* keyword followed by a method name and a function body.
* We use an if...else conditional to check if both _firstName and _lastName exist (by making sure they both return truthy values) and then return a different value depending on the result.
* We can access the calling object’s internal properties using *this*. In fullName, we’re accessing both this._firstName and this._lastName.
* In the last line, we call fullName on person. In general, getter methods do not need to be called with a set of parentheses. Syntactically, it looks like we’re accessing a property.

### Some of the advantages of getters are:
* Getters can perform an action on the data when getting a property.
* Getters can return different values using conditionals.
* In a getter, we can access the properties of the calling object using this.
* The functionality of our code is easier for other developers to understand.

Getter (and setter) methods can't share the same name as the getter/setter function. If we do that it will result in an infinite call stack error. A workaround is to add an underscore before the property name.

<br>

# Setters

Setter methods reassign values of existing properties within an object, safely.

```JS
const person = {
  _age: 37,
  set age(newAge){
    if (typeof newAge === 'number'){
      this._age = newAge;
    } else {
      console.log('You must assign a number to age');
    }
  }
};
person.age = 25 // calls the setter method and sets the new age property for the person object.
```

<br>

# Factory Functions

A factory function is a function that returns an object and can be reused to make multiple object instances.
They can also have parameters allowing us to customize the objects returned.

Let's make a monster factory for this example:
```JS
const monsterFactory = (name, age, energySource, catchPhrase) => {
  return { 
    name: name,
    age: age, 
    energySource: energySource,
    scare() {
      console.log(catchPhrase);
    } 
  }
};
```

now we have a function that makes monsters with a name, age, energy source and a catch phrase. So let's use it.

```JS
const ghost = monsterFactory('Ghouly', 251, 'ectoplasm', 'BOO!');
ghost.scare(); // 'BOO!'
```

The factory functions allow us to create object without writing a new literal every time we need a new object. We just call the function that makes the object we need.

<br>

# Property Value Shorthand

We can use this shorthand when the key and value are the same. Here's an example:

```JS
const monsterFactory = (name, age) => {
  return { 
    name,
    age 
  }
};
```
We just write the key without declaring the value and JS assumes the value is the same name as the key. Neat!

<br>

# Destructured Assignment

Studying this in Spooktober calls for spooky examples so let's use the following object:

```JS
const vampire = {
  name: 'Dracula',
  residence: 'Transylvania',
  preferences: {
    day: 'stay inside',
    night: 'satisfy appetite',
    food(){
        console.log('Loves blood & shish kebab')
    }
  }
};
```

Now let's say we need to assign the property residence to a variable that has the same name. Instead of going through the hassle of:

```JS
const residence = vampire.residence; 
```

we can simply use the destructured assignment:

```JS
const { residence } = vampire;
```

In destructured assignment, we create a variable with the name of an object’s key that is wrapped in curly braces { } and assign to it the object. 

We can even use destructured assignment to grab nested properties of an object:

```JS
const { day } = vampire.preferences; 
```

In essence, we extract a property and assign it to a variable that has the same name. This means we can also call the relevant methods on that variable now.

```JS
const {preferences} = vampire;
food.food() // logs in console Loves blood & shish kebab
```

<br>

# Built-in Object Methods

For example, we have access to object instance methods like: .hasOwnProperty() and .valueOf(). There are also useful Object class methods such as Object.assign(), Object.entries(), and Object.keys().

<a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object#Methods_of_the_Object_constructor' target=_blank> More built-in methods can be found in the documentation </a>

<br>
<br>

# SUMMARY

* The object that a method belongs to is called the calling object.
* The *this* keyword refers to the calling object and can be used to access properties of the calling object.
* Methods do not automatically have access to other internal properties of the calling object.
* The value of *this* depends on where the this is being accessed from.
* We cannot use arrow functions as methods if we want to access other internal properties.
* JavaScript objects do not have built-in privacy — however, there are conventions to follow to notify other developers about the intent of the code.
* The usage of an underscore before a property name means that the original developer did not intend for that property to be directly changed.
* Setter and getter methods allow for more detailed ways of accessing and assigning properties.
* Factory functions allow us to create object instances quickly and repeatedly.
* There are different ways to use object destructuring: one way is the property value shorthand and another is destructured assignment.
* As with any concept, it is a good skill to learn how to use the documentation with objects!

