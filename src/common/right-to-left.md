# Right-To-Left

Right To Left (RTL) can be enabled for Syncfusion JavaScript UI controls by calling [`enableRtl`](./api/base/staticFunctions#enablertl) with
`true`. This will render all the Syncfusion JavaScript controls in right to left direction. Find the code snippet
for this below.

{% tab template="common/right-to-left", es5Template="rtl-template" %}

```typescript
import { enableRtl } from '@syncfusion/ej2-base';
import { ListView } from '@syncfusion/ej2-lists';
import { data } from './datasource.ts';

// Enables Right to left alignment for all controls
enableRtl(true);

let rtlListObj: ListView = new ListView({
    dataSource: data,
    headerTitle: 'کاریں',
    showHeader: true,
    height: '350px'
    });
rtlListObj.appendTo('#listview');

```

{% endtab %}

## Enable RTL to individual control

To enable the RTL to an individual control, set the [`enableRtl`](./api/base/component#enablertl) property directly in its model options. For illustration, the [`enableRtl`](./api/base/component#enablertl) is added to the ListView control in following code snippet.

{% tab template="common/individual-rtl", es5Template="individual-rtl-template" %}

```typescript
import { ListView } from '@syncfusion/ej2-lists';
import { data } from './datasource.ts';
let rtlListObj: ListView = new ListView({
    dataSource: data,
    enableRtl: true,
    headerTitle: 'کاریں',
    showHeader: true,
    height: '350px'
    });
rtlListObj.appendTo('#listview');

```

{% endtab %}