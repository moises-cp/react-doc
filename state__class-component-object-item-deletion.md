# React Class Component State Object Item Deletion



```javascript
/** 
 * 	App.js
 */

import React, { Component } from "react";
import "./App.css";
import Person from "./Person/Person";

class App extends Component {
  state = {
    persons: [
      { id: "0", name: "Max", age: 28 },
      { id: "1", name: "Manu", age: 29 },
      { id: "2", name: "Stephanie", age: 26 },
    ],
  };

  /** 
   * Delete a person/object from the component persons state object
   */
  deletePersonHandler = (personIndex) => {
    // Make a local copy of the persons component state object
    const persons = [...this.state.persons];
    // Remove the person/object inside the local persons object based on the index
    persons.splice(personIndex, 1);
    /**
     * Overwrite everything in the component person state object with the local 
     * persons object.    
     */
    this.setState({ persons: persons });
  };


  render() {
    let persons = null;

    if (this.state.showPersons) {
      persons = (
        <div>
          {this.state.persons.map((person, index) => {
            return (
              <Person
                /**
                 * Pass the index to the return function named deletePersonHandler() 
                 * so when the Person component prop named click is called,
                 * the deletePersonHandler() method will remove that person
                 * based on the index provided.
                 */
                click={() => this.deletePersonHandler(index)}
              />
            );
          })}
        </div>
      );
    }

    return (
      <div className="App">
        {persons}
      </div>
    );
  }
}

export default App;

```

```javascript
/** 
 * 	Person.js
 */
 
 import React from "react";
import "./Person.css";

const person = (props) => {
  return (
    <div className="Person">
      /** 
       * When the p HTML tag is clicked, the prop named click will call 
       * deletePersonHandler(index) with the person index as 
       * the argument.
       */
      <p onClick={props.click}>
        I'm a Bill and I am 80 years old!
      </p>
    </div>
  );
};

export default person;
```

