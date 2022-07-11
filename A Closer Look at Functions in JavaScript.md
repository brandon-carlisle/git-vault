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
- JavaScript treats functions as first-class citizens
- This means functions are simply values
- Functions are just another "type" of object

- This means we can store functions in variables or properties
- We can pass functions as arguments to OTHER functions
- Can also return functions FROM functi