# Object-Oriented Programming (OOP) With [[JavaScript]]
## What is Object-Oriented Programming?
![[Screenshot 2022-08-27 at 18.34.48.png]]

![[Screenshot 2022-08-27 at 18.39.47.png]]

![[Screenshot 2022-08-27 at 18.41.38.png]]

![[Screenshot 2022-08-27 at 18.45.00.png]]

![[Screenshot 2022-08-27 at 18.48.35.png]]

![[Screenshot 2022-08-27 at 18.51.34.png]]

![[Screenshot 2022-08-27 at 18.54.17.png]]

## OOP in JavaScript
![[Screenshot 2022-08-27 at 19.02.35.png]]

![[Screenshot 2022-08-27 at 19.06.11.png]]

## Constructor Functions and the new Operator
We can use contructor functions to build an object using a function. A constructer functions is actually a completely normal function. The only difference is that we call a constructor function with the New operator.

![[Screenshot 2022-08-28 at 12.43.39.png]]

Using the new keyword there are a few steps when calling the function behind the scenes:

1) New {} is created
2) function is called, this = {}
3) {} linked to prototype
4) function automatically returns {}

![[Screenshot 2022-08-28 at 12.49.49.png]]

![[Screenshot 2022-08-28 at 12.50.15.png]]

We can check if something is an "instance" of a certain constructor function using instanceof:

![[Screenshot 2022-08-28 at 13.00.24.png]]
![[Screenshot 2022-08-28 at 13.00.43.png]]

## Prototypes
First each and every function in JavaScript automatically has a property called "Prototype", which of course includes contructor functions.

Every object that is created by a certain contructor function will get access to all the methods and properties that we define of the contructors prototype property.

![[Screenshot 2022-08-28 at 13.12.29.png]]
![[Screenshot 2022-08-28 at 13.09.43.png]]

We can now call this method on each function we have created from the constructor:

![[Screenshot 2022-08-28 at 13.12.54.png]]
![[Screenshot 2022-08-28 at 13.13.18.png]]

The brandon object doesn't actually contain the calc age method, but because of prototypal inheritance, it still has access to it.

## Prototypal Inheritance and The Prototype Chain
![[Screenshot 2022-08-28 at 13.35.21.png]]

![[Screenshot 2022-08-28 at 13.41.13.png]]

## ES6 Classes

This is how we used ES6 classes. We can create new objects with the classes in the same way using contructor functions.

![[Screenshot 2022-08-28 at 20.33.52.png]]
![[Screenshot 2022-08-28 at 20.35.06.png]]

We when create methods we create them INSIDE the class but OUTSIDE of the constructor method, so they are on the object prototype and not on each object, like this:

![[Screenshot 2022-08-28 at 20.38.20.png]]

Some notes about classes:

1) Classes are NOT hoisted (can't use before they are declared)
2) Just like functions, classes are 'first-class cititzens'
3) Classes are executed in strict mode

## Setters and Getters
Every object in JavaScript can have setter and getter properties. These are called accessor properties, while the more 'normal' properties are called data properites.

Getters and Setters are basically functions that get and set a value (but still look like normal properties on the outside).

![[Screenshot 2022-08-29 at 15.49.44.png]]

## Static Methods
A static method is defined on the class itself, so you cannot call the static method on an object. We could also say the method is in the 'namespace' of a certain class. It will NOT be available to use on the instances created from the class. 

How a static method looks like in a class, by using the static keyword: 

![[Screenshot 2022-08-29 at 17.56.51.png]]


## Object.create
Object.create is the third way we can implement prototypal inheritance, alonside contructor functions and ES6 Classes.

We can use this function to manually set the prototype of an object to any other object that we want. 

![[Screenshot 2022-08-30 at 19.52.31.png]]
![[Screenshot 2022-08-30 at 19.53.01.png]]

-----------------------------------------

How object.create works:

![[Screenshot 2022-08-30 at 20.06.11.png]]

In the real world, this method is used the least compared to constructor functions and classes, but we still use it to link prototypes between classes.

