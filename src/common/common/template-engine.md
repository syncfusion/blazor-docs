# Template Engine

Syncfusion JavaScript (Essential JS 2) has built-in template engine which provides options to compile
template string into a executable function. Then the generated executable function can
be used for rendering DOM element using desired data.

## Compiling

`compile` method from `ej2-base` can be used to convert our template strings into
executable functions.

{% tab template="common/template-engine", es5Template="template-engine-1" %}

```typescript

import { compile } from '@syncfusion/ej2-base';

// data
let data: object = { name: 'Aston Martin' };

// Compiling template string into executable function
let getDOMString: (data: object) => NodeList = compile('<div>${name}</div>');

// Using generated function to get output element collection
let output: NodeList = getDOMString(data);

// append html collection to element
document.getElementById('element').appendChild(output[0]);

```

{% endtab %}

## Available Template Syntax

| Name | Syntax | Description |
| --- | --- | --- | --- |
| Expression | `<div>${name}</div>`  | We have expression evolution as like ES6 expression string literals. |
| Dot Variable Access | `<div>${person.info.name}</div>` | Access the json variable with dot notation. |
| Variable Function | `<div>${name.toUpperCase()}</div>` | Utilize the variable function example, `name.toUpperCase()` |
| Window Function | `<div>${getCurrentTime()}div>` | Use window function inside template. Note: Here, `getCurrentTime()` is a function that defined in the window object. |
| Custom Helper Function | `<div>${covertToCurrency()}div>` | Use function that passed in [helper](#custom-helper) function. |
| IF Else Statement | `<div>` <br/> `${if(gender===”male”)}` <br/> `<span class=’ico-male’>Male</span>` <br/> `${else}` <br/> `<span class=’ico-female’>Female</span>` <br/> `${/if}` <br/> `</div>` | Branching statement in Template. |
| For Statement | `<div>` <br/> `${for(mark of marks)}` <br/> `<span>${mark}</span>` <br/> `${/for}` <br/> `</div>` | Use for looping inside template. |
| For Index value access | `<div>` <br/> `${for(mark of marks)}` <br/> `<span>${markIndex}</span>` <br/> `${/for}` <br/> `</div>` | Get the index value of item while using for statement. Use the variable `Index` that suffixed with loop item name. |

## Custom Helper

Custom helper function can be defined and passed to `compile` function. Refer to the following example.

{% tab template="common/template-engine", es5Template="custom-helper-template" %}

```typescript

import { compile } from '@syncfusion/ej2-base';

let customHelper: Object = {
    upperCase: (str: string) => {
        return str.toUpperCase();
    }
};

let data: object = { name: 'Aston Martin' };

let getDOMString: (data: object) => HTMLCollection = compile('<div>${upperCase(name)}</div>', customHelper);

let opElem: HTMLCollection = getDOMString(data);

document.getElementById('element').appendChild(opElem[0]);

```

{% endtab %}
