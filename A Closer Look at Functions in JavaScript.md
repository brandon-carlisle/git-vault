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
