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

 