# JSX Variable

<br>



## Example #1

```javascript
// Create varibale with its value set as null
let persons = null;

if (this.state.showPersons) {
  // Add JSX as a value to the persons variable
  persons = (
    <div>
      {this.state.persons.map((person, index) => {
        return (
          <Person
            click={() => this.deletePersonHandler(index)}
            name={person.name}
            age={person.age}
            key={person.id}
            changed={(event) => this.nameChangedHandler(event, person.id)}
          />
        );
      })}
    </div>
  );
}
```

