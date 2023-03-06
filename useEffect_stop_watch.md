```js
import React, { useEffect, useState } from "react";

export default function App() {
  const [counter, setCounter] = useState(0);
  const [stop, setStop] = useState(true);

  useEffect(() => {
    if (!stop) {
      const interval = setInterval(() => {
        setCounter((prev) => prev + 1);
      }, 1000);
      // unsubscribe from interval
      return () => {
        clearInterval(interval);
      };
    }
  }, [stop]);

  return (
    <div className="App">
      <h1>{counter}</h1>
      <button onClick={() => setStop(false)}>Start</button>
      <button onClick={() => setStop(true)}>Pause</button>
      <button
        onClick={() => {
          setCounter(0);
          setStop(false);
        }}
      >
        ReStart
      </button>
    </div>
  );
}
```
