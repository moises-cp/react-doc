# Inline Style

To use inline styles:

1. Create an object within `render(){}` block and add all the styles to it.

```javascript
const style = {
  backgroundColor: "white",
  font: "inherit",
  border: "1px solid blue",
  padding: "8px",
  cursor: "pointer",
};
```

2. Add the object with styles as a value to the style attribute

```javascript
<button style={style}>
  Toggle Persons
</button>
```





<br>

## Example

```javascript
/**
 *  App.js
 */

import React, { Component } from "react";
import "./App.css";

class App extends Component {
  render() {
    /**
     *  Create an object for the inline styles that will be need it
     */
    const style = {
      backgroundColor: "white",
      font: "inherit",
      border: "1px solid blue",
      padding: "8px",
      cursor: "pointer",
    };

    return (
      <div className="App">
        /**
         *  Assign the object with the styles as the value of the style attribute
         */
        <button style={style}>
          Toggle Persons
        </button>
      </div>
    );
  }
}

export default App;

```

