## Note about hooks

- Hooks can only be used inside of function components (not class components)
- Must be executed at the top level of the component (do not put inside if statements, functions or loops!)

## useState
When when use useState, we pass in the default state. For example, if we have a counter that we want to start at 4, we pass in 4 to useState when calling it.

useState will return an array of two values. The two values are: the state, and a function to update that state.

As useState always returns two values, we can use destructuring to take the two elements out of the array that is returned and store them into variables:

`const [count, setCount] = useState(0)`

Any time where you are setting state, and using the previous state to create the new value, you need to use the 'function version' of setting state. For example, instead of doing this:

```javascript
import { useState } from 'react';

export default function Counter() {
  const [count, setCount] = useState(0);

  function decrementCount() {
    setCount(count - 1);
  }

  return (
    <button onClick={decrementCount}>-</button>
      <span>{count}</span>
    <button>+</button>
  );
}
```
Do this instead:
```javascript
import { useState } from 'react';

export default function Counter() {
  const [count, setCount] = useState(0);

  function decrementCount() {
    setCount((prevCount) => prevCount - 1);
  }

  return (
    <button onClick={decrementCount}>-</button>
      <span>{count}</span>
    <button>+</button>
  );
}
```

We pass in the default state as an argument to useState. Setting the default value of useState will actually run everytime our component re-renders (so essentially everytime we set the set as this also triggers a re-render). 

This can be fine in a small counter, as we are just passing in the value 0 as the default state. But the problem is if we have a big computation as the initial state, it wouldn't be optimal to run the same code every time we re-render.

This can be addressed by passing a function into useState and an argument. This function will only the very first time your component renders.

```javascript
import { useState } from 'react';

export default function Counter() {
  const [count, setCount] = useState(() => 0);

  function decrementCount() {
    setCount((prevCount) => prevCount - 1);
  }

  return (
    <button onClick={decrementCount}>-</button>
      <span>{count}</span>
    <button>+</button>
  );
}
```

## useEffect

>In the React component lifecycle there is three main phases: 
>
>1) Component mounts when it's added to the screen
>2) Component updates when it receives new state
>3) Component unmounts when it's removed from the screen

useEffect is a function, that will take a function that you define as an argument. React will then run your function after it has updated the DOM.

In its default behaviour, the function inside of the useEffect will run every time the component is re-rendered. This behaviour can be changed by passing in a 'dependency' array as the second argument to the useEffect function.

When we pass in the dependency array, the function in the useEffect will only rerun if any of your dependencies change.

- If you add an empty dependency array, it will only run once when the component is first mounted.
- When you pass in state to the dependency array, it will also run whenever that state you pass in changes.

We can also add a 'clean-up' function to useEffect. This will run during unmount and also before every re-render with changed dependencies. This is very useful for things like 'disconnecting' and clearing intervals and timers etc. We just need to return the cleanup function from the useEffect.

Here's an example of a component updates every second:

```javascript

function App() {
const [seconds, setSeconds] = useState(1);

useEffect(() => {
	const timer = setInterval(() => {
	setSeconds(seconds + 1);
}, 1000);
	return () => clearInterval(timer);
});

return (
	<div className="App">
		<h1>Number of seconds is {seconds}</h1>
	</div>
	);
}

export default App
```


