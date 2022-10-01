# React State & Working with Events
## Listening to Events & Working with Event Handlers
In React, for all events in JavaScript there is a prop equivalent (such as the click event).

![[Screenshot 2022-10-01 at 14.07.25.png]]
## How Component Functions Are Executed
Reacting to events is the first important step, how can we now change what is on the screen? 

Lets say we reasign the props title inside of the ExpenseItem function and make it change on click of the button. It wouldn't work because the function has already been called once, and not again.

In react, we need a way to tell react that something has changed, and that a certain component should be reavaluated. - This is where react introduces a special concept called 'state'.

## Working with "State"
State is not a react specific concept, but it is a key concept in react. 

We first need to import a function called useState which will allow us to define values as state, where changes to the these values should reflect in the component function been called again
