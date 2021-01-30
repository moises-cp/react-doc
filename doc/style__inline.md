# Inline Style

- [Limitations](#limitations)
- [Usage](#usage)
- [Example 1](#example-1)
- [Tools](#tools)
  * [Radium](#radium)

<br><br>

## Limitations

- Unable to set sudo styles like: hover, active, etc.

<br><br>

## Usage

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

## Example 1

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



<br><br>



## Tools

### Radium

- Description
  
  - Radium is a set of tools to manage inline styles on React elements. It gives you powerful styling capabilities without CSS.
  
- Installation
  - `npm install --save radium`
  - [GitHub](https://github.com/formidablelabs/radium)
  - [NPM](https://www.npmjs.com/package/radium)
  
- Note
  
  - This package it is still maintain but it will not be adding new features.  Possibly discontinued.
  
- Usage

  - Hover

    - ```javascript
      const sytle = {
      	backgroundColor: 'green',
          color: 'white',
          /** 
           * This is where Radium comes into place 
           * by allowing the addition of hover state to this 
           * style object.
           */
          ':hover': {
              backgroundColor: 'lightgreen',
              color: 'white'
          }
      }
      
      /** 
       * Example of how to dynamically update the 
       * hover properties values in some other
       * part of the code.
       */
      style[':hover'] = {
          backgroundColor: 'lightred',
          color: 'black'
      }
      ```

      

