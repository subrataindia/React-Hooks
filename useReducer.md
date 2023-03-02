```js
import React, { useReducer } from "react";

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + action.payload };
    case "decrement":
      return { count: state.count - action.payload };
    default:
      throw new Error();
  }
}

const initialState = { count: 0 };

function App() {
  const [state, dispatch] = useReducer(reducer, initialState);
  return (
    <>
      <button onClick={() => dispatch({ type: "increment", payload:2 })}>+</button>
      {state.count}
      <button onClick={() => dispatch({ type: "decrement", payload:2 })}>-</button>
    </>
  );
}

export default App;

```
