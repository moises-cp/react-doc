# Dynamic Inline Style

<br>

## Example

```javascript
// Create the inline style object
const style = {
  backgroundColor: "white",
  font: "inherit",
  border: "1px solid blue",
  padding: "8px",
  cursor: "pointer",
};

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
            changed={(event) => this.nameChangedHandler(event, person.id)}
          />
        );
      })}
    </div>
  );
  // Change the background color value when the if statement is true
  style.backbroundColor = "red";
}
```
