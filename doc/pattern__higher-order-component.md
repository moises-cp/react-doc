# Higher-Order Component (HOC) Pattern

## Description

- It can be used on class and functional component

<br><br>

## Resources

- [React JS  >>  Higher-Order Components](https://reactjs.org/docs/higher-order-components.html)



<br><br>

## Example 1

```javascript
import PackgeName from './path/to/package';

class ComponentName extend Component {
    // ...Code
}

/** 
 * - This is where Higher-order component is applied.
 * - It works by a component wrapping an exported component
 *   to add some extra functionalities/features.
 * - E.g.  PackgeName(ComponentName)
 */
export default PackgeName(ComponentName);
```



