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

There are two ways to do this. First one is the dot operator.

object.property

