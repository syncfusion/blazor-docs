# Drag and Drop

Drag and Drop is supported through two libraries. Those are [`Draggable`](../api/base/draggable) and [`Droppable`](../api/base/droppable). Draggable makes DOM to be dragged using mouse or touch gestures and Droppable mark required DOM as droppable zone.

## Initializing draggable

You can make any element draggable by passing the element to Draggable constructor. Refer the following code snippet to enable draggable for DOM element.

 {% tab template="common/draggable-default", es5Template="draggable-default-template" %}

 ```typescript
 import {Draggable} from  '@syncfusion/ej2-base';

 let dragElement: HTMLElement = document.getElementById('element1');
 let draggable:Draggable = new Draggable(dragElement,{clone: false});
 ```

 {% endtab %}

## Creating droppable zone

You can convert any DOM element as a droppable zone, which accepts the draggable elements. Refer the following code snippet to enable droppable zone.

{% tab template="common/droppable-default", es5Template="droppable-default-template" %}

 ```typescript
 import { Droppable} from  '@syncfusion/ej2-base';

 let droppable: Droppable = new Droppable(document.getElementById('droppable'));
 ```

 {% endtab %}

## Defining drop action

To define drop action set [`drop`](../api/base/droppable#drop) callback function during droppable object creation. You can get details of dropped element through dropped element property in event argument. Refer the following code snippet to use basic drag and drop action.

{% tab template="common/drag-drop-action", es5Template="drag-drop-template" %}

 ```typescript
 import { Draggable, Droppable, DropEventArgs } from '@syncfusion/ej2-base';

let draggable: Draggable = new Draggable(document.getElementById('element1'), {
    clone: false
});
let droppable: Droppable = new Droppable(document.getElementById('droppable'), {
    drop: (e: DropEventArgs) => {
        e.droppedElement.querySelector('.drag-text').textContent = 'Dropped';
    }
});
 ```

 {% endtab %}

## See Also

[`Define handle element for Draggable`](../api/base/draggable#handle)<br/>
[`Restricting Draggable within container`](../api/base/draggable#dragarea)<br>
[`Visual feedback of draggable element`](../api/base/draggable#clone)<br>
[`Accepting specific drag element in droppable`](../api/base/droppable#accept)