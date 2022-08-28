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

