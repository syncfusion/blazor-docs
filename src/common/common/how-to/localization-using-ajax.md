# How to load the culture file in Essential JS 2 using Ajax

Ajax post can be used to load the `cldr` JSON files. Install the `cldr` data from npm package by using the following command.

```sh
npm install cldr-data
```

## Loading culture using Ajax

Locale files can be loaded based on culture name by using the Ajax post as shown in the following code snippet. Based on the selected culture, the `cldr` files will be loaded by using the following function.

```sh
//Function for loading locale files based on culture name
function loadCultureFiles(name:any) {
    let files: string[] = ['ca-gregorian.json', 'numbers.json', 'timeZoneNames.json'];
     let loadCulture = function (prop:any) {
        let val:string, ajax: Ajax;
        if (name === 'ar' && prop === files.length - 1) {
            ajax = new Ajax( './node_modules/cldr-data/supplemental/' + files[prop], 'GET', false);
        } else {
            ajax = new Ajax( './node_modules/cldr-data/main/' + name + '/' + files[prop], 'GET', false);
        }
        ajax.onSuccess = function (value:any) {
            val = value;
            loadCldr(JSON.parse(val));
        };
        ajax.send();
    };
    for (let prop = 0; prop < files.length; prop++) {
        loadCulture(prop);
    }
}
loadCultureFiles('de');
```

## Loading translations

To load the translation object in your application, use the load function of L10n class.

```sh
//loading locale files
L10n.load({
    'de': {
        'calendar': { today: 'heute' },
    },
});
```

## Loading CLDR files using loadCldr function

Pass the locale files into the `loadCldr` function as shown in the following example. The `setCulture` method allows you to set the required culture.

```sh
import { Calendar } from '@syncfusion/ej2-calendars';
//import the loadCldr from ej2-base
import { loadCldr, L10n, Ajax, setCulture } from '@syncfusion/ej2-base';

declare var require: any;
//loading locale files
L10n.load({
    'de': {
        'calendar': { today: 'heute' },
    },
});

//Function for loading locale files based on culture name
function loadCultureFiles(name:any) {
    let files: string[] = ['ca-gregorian.json', 'numbers.json', 'timeZoneNames.json'];
     let loadCulture = function (prop:any) {
        let val:string, ajax: Ajax;
        if (name === 'ar' && prop === files.length - 1) {
            ajax = new Ajax( './node_modules/cldr-data/supplemental/' + files[prop], 'GET', false);
        } else {
            ajax = new Ajax( './node_modules/cldr-data/main/' + name + '/' + files[prop], 'GET', false);
        }
        ajax.onSuccess = function (value:any) {
            val = value;
            loadCldr(JSON.parse(val));
        };
        ajax.send();
    };
    for (let prop = 0; prop < files.length; prop++) {
        loadCulture(prop);
    }
}
loadCultureFiles('de');

let calendarObject: Calendar = new Calendar({
    //sets the locale.
    locale: 'de'
});

calendarObject.appendTo('#element');
setCulture('de');calendarObject.appendTo('#element');
setCulture('de');
```

All components’ localized texts are provided in the ej2-locale [`GitHub`](https://github.com/syncfusion/ej2-locale) repository. Also find the example sample from this [`link`](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ajax-locale-1067269484.zip).
