## useState

useState is one of the most common built in React hooks. 
It returns a value and a setter function.

A common patten for react hooks is to return an array with different values. In this case the first value is our **stateful** value and the second value is our setter function. 

```js
const [state, setState] = useState('hello world!');
```

You can use a stateful value just like a variable within your return method and within other functions within your component. 

In this example we print out a name by reading the stateful value `name`.
```js
import { useState } from 'react';

const MyComponent = () => {
  const [name, setName] = useState('Bob');

  return (
    <div>
      <p>Hello, { name }.</p>
    </div>
  )
};
```

The setter function can be used to update your stateful value. In this example we update a `count` using the `setCount` setter function.
```js
import { useState } from 'react';

const MyComponent = () => {
  const [count, setCount] = useState(0);

  const handleAddButtonClick = () => {
    setCount(count + 1);
    // or you can use a value returned from the setter e.g:
    // setCount(count => count + 1);
  };

  return (
    <div>
      <p>The count is: { count }.</p>
      <button onClick={handleAddButtonClick}>
        Add
      </button>
    </div>
  )
};
```
