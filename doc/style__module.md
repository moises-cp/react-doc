# CSS Modules

## Description

- Unlike *styled-component* and *JS inline styles*, with CSS modules, you will be writing regular CSS code.
- Scoped styles.
- Available on React Scripts 2.x or higher (without modifying config files).

<br><br>

## Example 1

Person.module.css

```css
/**
 * Write the styles needed for the component.
 */
.Person {
  width: 60%;
  margin: 16px auto;
  border: 1px solid #eee;
  box-shadow: 0 2px 3px #ccc;
  padding: 16px;
  text-align: center;
}

@media (min-width: 500px) {
  .Person {
    width: 450px;
  }
}
```

- The CSS file name needs to include **.module**
  - Ex.  *filename.module.css*

<br>



Person.js

```javascript
import React from "react";
/**
 * - Import the CSS file
 * - Assign its styles to an object named classes
 */
import classes from './Person.module.css';

const person = (props) => {
  return (
    /**
     * Add one of the styles from the classess object
     */
    <div className={classes.Person}>
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

