# Class Component Object Update



```javascript
/**
 *	App.js
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
   * Update the persons object that is in the class component state object
   */
  nameChangedHandler = (event, id) => {
    /**
     * Iterate through the object name persons that is inside the 
     * class component state object and return the position 
     * of the object that match the provided id
     */
    const personIndex = this.state.persons.findIndex((p) => {
      return p.id === id;
    });
	 
    /** 
     * Create a local object named person and add as a value 
     * the specified object from the object named persons in
     * the class component state object 
     */
    const person = {
      ...this.state.persons[personIndex],
    };

    /**
     * From the local person object, replace the name property value
     * with the value from the event target. 
     */
    person.name = event.target.value;

    /** 
     * Create a local persons object and add as the value
     * the persons object from the class component state object
     */
    const persons = [...this.state.persons];
    /**
     * Replace everything inside the specified object in the
     * local persons object with the the local person object
     */
    persons[personIndex] = person;
    /**
     * From the class component object named persons,
     * replace everthing inside it, with the local object named persons 
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
                click={() => this.deletePersonHandler(index)}
                name={person.name}
                age={person.age}
                key={person.id}
        		/**
        		 * Assign an annonimous arrow function to the prop named changed
        		 * that will be calling the nameChangedHandler() method with the
        		 * event and provided id as the arguments when the prop is called
        		 * in the Person component
        		 */
                changed={(event) => this.nameChangedHandler(event, person.id)}
              />
            );
          })}
        </div>
      );
    }

    return (
      <div className="App">
        <h1>Hi, I'm a React App</h1>
        <p>This is really working!</p>
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

<br>

```javascript
/**
 *	Person.js
 */

import React from "react";
import "./Person.css";

const person = (props) => {
  return (
    <div className="Person">
      <p onClick={props.click}>
        I'm a {props.name} and I am {props.age} years old!
      </p>
      <p>{props.children}</p>
	  /**
	   * When the user type anything in the input field, the onChange event will
	   * call the function attached to the prop named changed.
	   */
      <input type="text" onChange={props.changed} value={props.name} />
    </div>
  );
};

export default person;
```
