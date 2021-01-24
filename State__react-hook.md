# React Hook

<br>

## Description

### Purpose

- Provide state management to functional component.

<br><br><br>

## Example of Function Component Using State React Hook

```javascript
import React, { useState } from 'react';

const componentName = props => {
    useState({
        property1: [
            { key1: 'key1-value', key2: 'key2-value' },
            { key1: 'key1-value', key2: 'key2-value' },
            { key1: 'key1-value', key2: 'key2-value' }
        ],
        property2: 'some value'
    });
    
	return ();
}

export default componentName;
```

- `render()` is no longer needed;

- It returns just JSX

- To use React Hooks, import the **useState** method

  ```javascript
  import React, { useState } from 'react';	
  ```

  