# How to load the culture file in Essential JS 2

In Essential JS 2, the culture file can be loaded by using the `loadCldr` function. Use the following command to install `cldr` JSON files from the npm package.

```sh
npm install cldr-data
```

## Loading culture

Load the required locale and supplemental files from `cldr` in your application. Ensure all the locale related files are loaded correctly in your application.

```sh
import * as n1 from  '../../node_modules/cldr-data/main/de/currencies.json'
import * as n2 from '../../node_modules/cldr-data/main/de/timeZoneNames.json';
import * as n3 from '../../node_modules/cldr-data/main/de/numbers.json';
import * as n4 from '../../node_modules/cldr-data/main/de/ca-gregorian.json';
import * as s from '../../node_modules/cldr-data/supplemental/currencyData.json';
import * as s2 from '../../node_modules/cldr-data/supplemental/numberingSystems.json';
```

## Loading translations

To load the translation object in the application, use the load function of L10n class.

```sh
L10n.load({
    'de': {
        'calendar': { today: 'heute' }
    }
});
```

## Loading CLDR files using loadCldr function

Pass the locale files into the `loadCldr` function as shown in the following example. The `setCulture` method allows you to set the required culture.

```sh
import { Calendar } from '@syncfusion/ej2-calendars';
import { Tab } from '@syncfusion/ej2-navigations';
import {L10n, setCulture, loadCldr} from '@syncfusion/ej2-base';
import * as n1 from  '../../node_modules/cldr-data/main/de/currencies.json'
import * as n2 from '../../node_modules/cldr-data/main/de/timeZoneNames.json';
import * as n3 from '../../node_modules/cldr-data/main/de/numbers.json';
import * as n4 from '../../node_modules/cldr-data/main/de/ca-gregorian.json';
import * as s from '../../node_modules/cldr-data/supplemental/currencyData.json';
import * as s2 from '../../node_modules/cldr-data/supplemental/numberingSystems.json';
L10n.load({
    'de': {
        'calendar': { today: 'heute' }
    }
});
//Initialize calendar component.
let calendarObject: Calendar = new Calendar();
//Render initialized calendar.
calendarObject.appendTo('#element');
loadCldr(n1, n2, n3, n4, s, s2);
setCulture('de');
 ```

All components’ localized texts are provided in the ej2-locale [`GitHub`](https://github.com/syncfusion/ej2-locale) repository. Also find the example sample from this [`link`](http://www.syncfusion.com/downloads/support/directtrac/general/ze/localization-1218148352.zip).
