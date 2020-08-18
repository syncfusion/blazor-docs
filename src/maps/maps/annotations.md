# Annotations

Annotations are used to mark a specific area of interest in the map area with texts, shapes, or images. You can add any number of annotations to the maps.

## Annotation

By using the [`content`](../api/maps/annotation/#content-string) property of [`annotation`](../api/maps/annotation) object, you can either specify the ID of an element or specify the code to create a new element that needs to be displayed in the gauge area.

```html
<script id='annotation' type="text/x-template">
    <div id='template'>
        <img src='src/maps/images/flight.png'>
    </div>
</script>
```

```typescript

import { Maps, Annotations } from '@syncfusion/ej2-maps';
import { world_map } from './world-map.ts';
Maps.Inject(Annotations);

let maps: Maps = new Maps({
        annotations: [
            {
                content: '#annotation',
                x: '0%', y: '50%'
            }
        ],
        layers: [
            {
                shapeData: world_map,
            }
        ]
    });
    maps.appendTo('#element');

```

## Annotation customization

### Changing the z-order

You can change the z-order of an annotation element using the [`zIndex`](../api/maps/annotation/#zindex-string) property.

{% tab template= "maps/default-map",sourceFiles="index.ts,index.html,index.css" , isDefaultActive=true , es5Template = "annotationZOrder" %}

```typescript

import { Maps } from '@syncfusion/ej2-maps';
import { world_map } from './world-map.ts';
let map: Maps = new Maps({
   annotations: [
            {
                content: '<div id="first"><h1>Maps</h1></div>',
                x: '0%', y: '50%',
                zIndex: '-1'
            }
   ],
   layers: [
        {
             shapeData: world_map
        }
    ]
}, '#element');

```

{% endtab %}

### Positioning of annotation

You can place an annotation anywhere in gauge area by specifying pixel values to the [`x`](../api/maps/annotation/#x-number) and [`y`](../api/maps/annotation/#y-number) properties.

{% tab template= "maps/default-map",sourceFiles="index.ts,index.html,index.css" , isDefaultActive=true , es5Template = "annotationPosition" %}

```typescript

import { Maps } from '@syncfusion/ej2-maps';
import { world_map } from './world-map.ts';
let map: Maps = new Maps({
   annotations: [
            {
                content: '<div id="first"><h1>Maps</h1></div>',
                x: '20%', y: '50%',
                zIndex: '-1'
            }
   ],
   layers: [
        {
             shapeData: world_map
        }
    ]
}, '#element');

```

{% endtab %}

### Alignment of annotation

You can align annotations using the [`horizontalAlignment`](../api/maps/annotation/#horizontalalignment-string) and [`verticalAlignment`](../api/maps/annotation/#verticalalignment-string) properties.

{% tab template= "maps/default-map",sourceFiles="index.ts,index.html,index.css" , isDefaultActive=true , es5Template = "annotationAlignment" %}

```typescript

import { Maps } from '@syncfusion/ej2-maps';
import { world_map } from './world-map.ts';
let map: Maps = new Maps({
   annotations: [
            {
                content: '<div id="first"><h1>Maps</h1></div>',
                verticalAlignment: 'Center',
                horizontalAlignment: 'Center',
                x: '20%', y: '50%',
                zIndex: '-1'
            }
   ],
   layers: [
        {
             shapeData: world_map
        }
    ]
}, '#element');

```

{% endtab %}
