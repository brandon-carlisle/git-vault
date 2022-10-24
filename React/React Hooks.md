- Hooks can only be used inside of function components (not class components)
- Must be executed at the top level of the component (do not put inside if statements, functions or loops!)

## useState
When when use useState, we pass in the default state. For example, if we have a counter that we want to start at 4, we pass in 4 to useState when calling it.

useState will return an array of two values. The two values are: the state, and a function to update that state.

As useState always returns two values, we can use destructuring to take the two elements out of the array that is returned and store them into variables:

`const [count, setCount] = useState(0)`

Any time where you are setting state, and using the previous state to create the new value, you need to use the 'function version' of setting state. For example, instead of