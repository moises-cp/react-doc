# Class Component Vs Function Component



## Function Component

```javascript
import React from 'react';

const componentName = (prop) => {
    return (
        <div>
        	<p>Something to return!</p>
        </div>
    );
}

export default componentName;
```

- Recommended for when the component does not need to have *state*.



## Class Component

```javascript
import React, { Component } from 'react';

class ComponentName extends Component {

	render() {
		return (
        
        );
	}
}

export default ComponentName;
```

- Recommended for when the component will need a *state*.