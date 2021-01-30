# React Styled-Components
- [Installation](#installation)
- [Resources](#resources)
- [Usage](#usage)
  * [Examples 1 - Style Div](#examples-1---style-div)
    + [Before](#before)
    + [After](#after)
  * [Example 2 - Style Button](#example-2---style-button)
    + [Before](#before-1)
    + [After](#after-1)

<br>


## Installation

`npm install --save styled-components`

<br><br>



## Resources

- [Styled Components Website](https://styled-components.com/)

<br><br>

## Usage

### Examples 1 - Style Div

#### Before

```javascript
import React from "react";
import "./Person.css";

const person = (props) => {
  return (
    <div className="Person">
      <p onClick={props.click}>
        I'm a {props.name} and I am {props.age} years old!
      </p>
      <p>{props.children}</p>
      <input type="text" onChange={props.changed} value={props.name} />
    </div>
  );
};

export default person;
```



#### After

```javascript
import React from "react";
import styled from 'styled-components';

/**
 * - Removed >> import "./Person.css";
 * - Moved its styles to the component below named StyleDiv.
 * - styled.div returns a component. 
 */
const StyleDiv = styled.div`
  width: 60%;
  margin: 16px auto;
  border: 1px solid #eee;
  box-shadow: 0 2px 3px #ccc;
  padding: 16px;
  text-align: center;

  @media (min-width: 500px) {
    width: 450px;
  }
`;

const person = (props) => {
  return (
    /**
     * <div className="Person"> has been replaced with <StyledDiv>
     * Every methods from styled will return a React component
     */
    <StyleDiv>
      <p onClick={props.click}>
          I'm a {props.name} and I am {props.age} years old!
        </p>
        <p>{props.children}</p>
        <input type="text" onChange={props.changed} value={props.name} />
    </StyleDiv>
  );
};

export default person;

```





### Example 2 - Style Button

#### Before

```javascript
import React, { Component } from "react";
import "./App.css";
import Person from "./Person/Person";

class App extends Component {
  /* ... code  */

  render() {
    const style = {
      backgroundColor: "green",
      color: 'white',
      font: "inherit",
      border: "1px solid blue",
      padding: "8px",
      cursor: "pointer",
    };
      
    /* ... code  */

    return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
        <p className={ classes.join(' ') }>This is really working!</p>
        <button style={style} onClick={this.togglePersonsHandler}>
          Toggle Persons
        </button>
        {persons}
      </div>
    );
  }
}

export default App;
```



#### After

```javascript
import React, { Component } from "react";
// import styled package
import styled from 'styled-components';
import "./App.css";
import Person from "./Person/Person";

/**
 * - Create a style component for the button and
 *   add the styles to it.
 * - Add the styles to it
 */
const StyledButton = styled.button`
  background-color: green;
  color: white;
  font: inherit;
  border: 1px solid blue;
  padding: 8px;
  cursor: pointer;

  &:hover {
    background-color: lightgreen;
    color: black;
  }
`;

class App extends Component {
  /* ... code  */

  render() {
    /* ... code  */

    return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
        <p className={ classes.join(' ') }>This is really working!</p>
		/**
		 * - Replace button tag with StyledButton 
		 * - Removed style={style} because is no longer relevant
		 */
        <StyledButton onClick={this.togglePersonsHandler}>
          Toggle Persons
        </StyledButton>
        {persons}
      </div>
    );
  }
}

export default App;
```

