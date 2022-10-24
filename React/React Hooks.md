- Hooks can only be used inside of function components (not class components)
- Must be executed at the top level of the component (do not put inside if statements, functions or loops!)

## useState
When when use useState, we pass in the default state. For example, if we have a counter that we want to start at 4, we pass in 4 to useState when calling it.

useState will return an array of two values. The two values are: the state, and a function to update that state.

As useState always returns two values, we can use destructuring to take the two elements out of the array that is returned and store them into variables:

`const [count, setCount] = useState(0)`

Any time where you are setting state, and using the previous state to create the new value, you need to use the 'function version' of setting state. For example, instead of doing this:

```
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
```
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

```
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