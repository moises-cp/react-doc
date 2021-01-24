# Class Component Vs Function Component

## Function Component

```javascript
import React from "react";

const componentName = (prop) => {
  return (
    <div>
      <p>Something to return!</p>
    </div>
  );
};

export default componentName;
```

- State
  - Recommended for when the component does not need to use the traditional _state_.
  - It can use *React Hooks*.

<br><br><br>

## Class Component

```javascript
import React, { Component } from 'react';

class ComponentName extends Component {

	render() {
		return ();
	}
}

export default ComponentName;
```

- State
  - It can use traditional component state management.
    - `sate = {};`
    - `*this*.setState({ property: value });`
