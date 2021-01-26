# Conditional Message





```javascript
/**
 *  Validation.js
 *
 *  Instead of using a ternary in the return block statement,
 *  setup the logic of what needs to be in the variable
 *  just like in the example below.
 */

import React from 'react';

const validation = ( props ) => {
    let validationMessage = 'Text long enough';

    if (props.inputLength <= 5) {
        validationMessage = 'Text too short';
    }

    return (
        <div>
            /**
             *  The value of the variable validationMessage is determined
             *  by the default value alreay provided or by the if statement
             *  when true
             */
            <p>{validationMessage}</p>
        </div>
    );
};

export default validation;
```

