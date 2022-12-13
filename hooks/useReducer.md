## useReducer

The `useReducer` hook is one of those that you might not use very often but it is very useful when you need to manage complex stateful values.

`useReducer` is a hook that lets you manage stateful values in a similar way to `useState` but it gives you more control over how you update your stateful value.

If you are familiar with Redux then `useReducer` uses a similar pattern to Redux.

For example for a counter app you might do something like this:

```js
import { useReducer } from 'react';

const initialState = { count: 0 };

const reducer = (state, action) => {
  switch (action.type) {
    case 'INCREMENT':
      return { count: state.count + 1 };
    case 'DECREMENT':
      return { count: state.count - 1 };
    default:
      return state;
  }
};

const MyComponent = () => {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      <p>The count is: { state.count }.</p>
      <button onClick={() => dispatch({ type: 'INCREMENT' })}>
        Add
      </button>
      <button onClick={() => dispatch({ type: 'DECREMENT' })}>
        Subtract
      </button>
    </div>
  )
};
```

Taking a look at the above example we can see that we have a `reducer` function that takes in a `state` and an `action` and returns a new state.

The `reducer` function is passed `useReducer` as the first argument and the `initialState` is passed as the second argument.

The `useReducer` hook returns an array with two values. The first value is the current state and the second value is a `dispatch` function.

The `dispatch` function is used to update the state. In the above example we pass an object with a `type` property to the `dispatch` function. The `type` property is used to determine which action within the `case` to take.

