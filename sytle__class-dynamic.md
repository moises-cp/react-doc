# Dynamic Class Styles



## Example 1

CSS

```css
.red {
  color: red;
}

.bold {
  font-weight: bold;
}
```



```javascript
// Create an array to store the CSS classes name
const classes = [];
// Set condition to add a CSS class to the classes array when true
if(this.state.persons.length <= 2 ) {
  classes.push('red');
}
// Set condition to add a CSS class to the classes array when true
if(this.state.persons.length <= 1 ) {
  classes.push('bold');
}

return (
  <div className="App">
    <h1>Hi, I'm a React App</h1>
    
    /** 
     * Add classes array as a className value and
     * use the join array method to replace the commas with
     * empty space and convert the array into a string
     */
    <p className={ classes.join(' ') }>This is really working!</p>

    <button style={style} onClick={this.togglePersonsHandler}>
      Toggle Persons
    </button>
    {persons}
  </div>
);
```

