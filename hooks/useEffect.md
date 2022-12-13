## useEffect 

"The Effect Hook lets you perform side effects in function component": [source](https://reactjs.org/docs/hooks-effect.html)

useEffect is another very common hook to see out in the wild. It lets you preform lifecycle events within a functional component as well as responding to values changing within your component. 

For example, if you want to run some code one your component has been rendered to the DOM (for example an API call) you can use `useEffect` to do this:

In this example we have a "todo" app where we want to fetch existing todo items from an API: 
```js
import { useEffect } from 'react';

const MyComponent = () => {
  const [todos, setTodos] = useState([]);

  const getTodoItems = async () => {
    const response = await fetch('https://someapi.com/todos')
      .then(response => response.json());
    
    setTodos(response);
  };

  useEffect(async () => {
    getTodoItems();
  }, []);

  return (
    <ul>
      { todos.map((todo, index) => (
        <li key={`todo-${index}`}>
          { todo.task }: { todo.isComplete ? 'done' : 'incomplete' }
        </li>
      ))}
    </ul>
  )
};
```

You can also use `useEffect` to respond to changes in your component. For example, if you want to update the title of your page when the `name` stateful value changes you can do something like this where you pass a dependency array to `useEffect` which will only run the effect if the values in the array have changed:

```js
import { useEffect } from 'react';

const MyComponent = () => {
  const [name, setName] = useState('Bob');

  useEffect(() => {
    document.title = `Hello, ${name}`;
  }, [name]);

  return (
    <div>
      <p>Hello, { name }.</p>
    </div>
  )
};
```
