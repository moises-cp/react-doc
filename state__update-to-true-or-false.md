# State Property Update To True or False

In this example, when the button `Toggle Persons` is clicked:

1. The  `togglePersonsHandler` method takes care of updating the state property named `showPerson` to `true` or `false` by using the <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT" target="_blank" rel="noopener">logical Not operator</a> that will assign the opposite value.



```javascript
import React, { Component } from "react";
import "./App.css";
import Person from "./Person/Person";

class App extends Component {
  state = {
    showPersons: false,
  };

  /**
   * Update the property showPerson that is in the state object
   */
  togglePersonsHandler = () => {
    /**
     * Create a variable named doesShow and add as the value,
     * the value from the propery showPersons that is in the state object
     */
    const doesShow = this.state.showPersons;
    /**
     * Replace the value of the showPerson propery that is the
     * state object with the value of the local variable named doesShow.
     */
    this.setState({ showPersons: !doesShow });
  };

  render() {
    let persons = null;

    if (this.state.showPersons) {
      persons = (
        <div></div>
      );
    }

    return (
      <div className="App">
        /**
         * When the button is clicked, the onClick event handler will
         * call the function/method togglePersonsHandler
         */
        <button onClick={this.togglePersonsHandler}>
          Toggle Persons
        </button>
        {persons}
      </div>
    );
  }
}

export default App;

```

