## React workshop

This workshop is intended to get you to the point you're comfortable with React relatively quickly.
We'll cover:

  - components
    - class components
    - functional components 
  - hooks and state


```js
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    <div>
      { this.props.children }
    </div>
  }
}
```

```js
const MyComponent = ({ children }) => {
  return (
    <div>
      { children }
    </div>
  )
};
```

```typescript
type Props = {
  children?: React.ReactNode;
};

const MyComponent = ({ children }: Props) => {
  return (
    <div>
      { children }
    </div>
  )
};
```
