## A Closer Look at Functions in [[JavaScript]]
### Default Parameters
Sometimes it's useful to have functions where some parameters are set by default, this way we don't need to pass them in manually incase we don't want to change from the default.

![[Code_RnyzI2vSg7.png]]

Here we set some default values on the number of passenger and the price of the booking.

### How passing arguments works: Value vs. Reference
When we pass a reference type to a function, what is copied is really just a reference to the object in the memory heap. 

When we pass a primitive type to a function is just the same as copying the value to a new variable.

We need to be careful of passing objects to functions in big codebases.

### First-class and Higher-Order functions
#### First-class functions
- JavaScript treats functions as first-class citizens
- This means functions are simply values
- Functions are just another "type" of object

- This means we can store functions in variables or properties:

![[chrome_u7XPkEvZAT.png]]
- We can pass functions as arguments to OTHER functions:

![[chrome_zkuz6ZtyvH.png]]

- Can also return functions FROM functions

- We can call methods on functions:

![[chrome_NE41c5KVge.png]]

#### Higher-order functions
- A function that receives another functions as an arguments, that returns a new functions, or both
- This is only possible because of first-class functions

1) Function that receives another function:

![[chrome_0WGo49Akza.png]]

2) Function that returns another function:

![[chrome_NVK8Ui4uOc.png]]

#### Functions returning Functions

![[Code_xnIJtTngmg.png]]

#### The Call and Apply Methods
The call method allows us to manually and explicitly set the this keyword of any function we want to call

The apply method works in the same way except it takes in the method and an array with the call parameters. -- Not used as much now because we can use the spread operator with the call method.

#### The bind method
Just like the call method, the bind method allows us to manually set the this keyword for any function call - but it does immeditely call the function, instead it returns a new function where the this keyword is bound. It is set to whatever value we pass into bind.

Example of using the bind method on a event listener, because when we use an event listener, the this keyword becomes whichever element we are selecting, in this case it would be the buy button:

![[Code_U2IIAWOTwM.png]]

-------

Partial application  -

Used to create a new function with one or more of its arguments already 'set', or partially applied. 

Here we use partial applicating using the bind method, where we set the tax rate:

![[Code_PQj7pL1yGI.png]]

### Immediately Invoked Functions (IIFE)
Sometimes in JavaScript we need a function that is only executed once, and then never again. Basically a function that disapears right after it is called.

![[Code_ML4QGEPZGl.png]]

Same with an arrow function:

![[Code_yxj6GooOhX.png]]

#### Why was this pattern invented?

We already know that functions create scopes. One scope does not have access to variables from an inner scope. All data that is inside a scope are encapsulated (private).

If we used var to create the variable inside a function it would not be function scoped, unlike let and const

### Closures
A closure is not something we manually create, like a new array or function. A closure simply happens in certain situations.

We can say a closure makes a function remember all the variables that existed at the functions 'birth place'.

Any function always has access to the variable enviroment of the execution context in which the function was created.
Closure: Variable enviroment attached to the function, exactly as it was at the time and place the function was created.

JavaScript first looks for variables in a closure before the scope chain (has priority).

