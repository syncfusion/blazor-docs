# Built-in Themes

The Syncfusion Blazor library provides the following list of built-in themes:

1. Bootstrap 4
2. Bootstrap
3. Google’s Material
4. Microsoft Office’s Fabric
5. High Contrast

> The Syncfusion Bootstrap theme is designed based on `Bootstrap v3`, whereas the Bootstrap4 theme is designed based on `Bootstrap v4`.

## Theme file syntax and references

* The Syncfusion Blazor themes are available as static web assets in the `Syncfusion.Blazor` and `Syncfusion.Blazor.Themes` NuGet packages.

* Add the below link reference inside the `<head>` element of the `~/Pages/_Host.cshtml` file for Blazor server app or `~/wwwroot/index.html` file for Blazor WebAssembly app.

    If you are using [individual NuGet packages](http://blazor.syncfusion.com/documentation/nuget-packages/) in your application, then use the below reference link.
    ```html
    <head>
        ....
        ....
        <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
    </head>
    ```

    If you are using `Syncfusion.Blazor` NuGet package in your application, then use the below reference link.
    ```html
    <head>
        ....
        ....
        <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    </head>
    ```

    > The below theme file names can be replaced with the above links.
    > * bootstrap4.css
    > * bootstrap.css
    > * bootstrap-dark.css
    > * fabric.css
    > * fabric-dark.css
    > * highcontrast.css
    > * material.css
    > * material-dark.css

## CDN reference

The Syncfusion Blazor themes also available in the CDN.

```html
<head>
    ....
    ....
    <link href="https://cdn.syncfusion.com/blazor/{:version:}bootstrap4.css" rel="stylesheet" />
</head>
```

## Common Variables

The following list of common variables is used in the Syncfusion Blazor library themes for all UI components. You can change these variables to customize the corresponding theme.

### Bootstrap 4

| Name | Value |
| ------------- | ------------- |
| `$white` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$gray-100` | ![#f8f9fa](https://ej2.syncfusion.com/download/documentation/svg/f8f9fa.svg) `#f8f9fa` |
| `$gray-200` | ![#e9ecef](https://ej2.syncfusion.com/download/documentation/svg/e9ecef.svg) `#e9ecef` |
| `$gray-300` | ![#dee2e6](https://ej2.syncfusion.com/download/documentation/svg/dee2e6.svg) `#dee2e6` |
| `$gray-400` | ![#ced4da](https://ej2.syncfusion.com/download/documentation/svg/ced4da.svg) `#ced4da` |
| `$gray-500` | ![#adb5bd](https://ej2.syncfusion.com/download/documentation/svg/adb5bd.svg) `#adb5bd` |
| `$gray-600` | ![#6c757d](https://ej2.syncfusion.com/download/documentation/svg/6c757d.svg) `#6c757d` |
| `$gray-700` | ![#495057](https://ej2.syncfusion.com/download/documentation/svg/495057.svg) `#495057` |
| `$gray-800` | ![#343a40](https://ej2.syncfusion.com/download/documentation/svg/343a40.svg) `#343a40` |
| `$gray-900` | ![#212529](https://ej2.syncfusion.com/download/documentation/svg/212529.svg) `#212529` |
| `$black` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000` |
| `$blue` | ![#007bff](https://ej2.syncfusion.com/download/documentation/svg/007bff.svg) `#007bff` |
| `$indigo` | ![#6610f2](https://ej2.syncfusion.com/download/documentation/svg/6610f2.svg) `#6610f2` |
| `$purple` | ![#6f42c1](https://ej2.syncfusion.com/download/documentation/svg/6f42c1.svg) `#6f42c1` |
| `$pink` | ![#e83e8c](https://ej2.syncfusion.com/download/documentation/svg/e83e8c.svg) `#e83e8c` |
| `red` | ![#dc3545](https://ej2.syncfusion.com/download/documentation/svg/dc3545.svg) `#dc3545` |
| `$orange` | ![#fd7e14](https://ej2.syncfusion.com/download/documentation/svg/fd7e14.svg) `#fd7e14` |
| `$yellow` | ![#ffc107](https://ej2.syncfusion.com/download/documentation/svg/ffc107.svg) `#ffc107` |
| `$green` | ![#28a745](https://ej2.syncfusion.com/download/documentation/svg/28a745.svg) `#28a745` |
| `$teal` | ![#20c997](https://ej2.syncfusion.com/download/documentation/svg/20c997.svg) `#20c997` |
| `$cyan` | ![#17a2b8](https://ej2.syncfusion.com/download/documentation/svg/17a2b8.svg) `#17a2b8` |

### Bootstrap

| Name | Value (Default Theme) | Value (Dark Theme) |
| ------------- | ------------- | ------------- |
| `$brand-primary` | ![#317ab9](https://ej2.syncfusion.com/download/documentation/svg/317ab9.svg) `#317ab9` | ![#0070f0](./images/bootstrap-dark/0070f0.png) `#0070f0` |
| `$brand-primary-darken-10` | ![#3071a9](https://ej2.syncfusion.com/download/documentation/svg/3071a9.svg) `#3071a9` | ![#0058bd](./images/bootstrap-dark/0058bd.png) `#0058bd` |
| `$brand-primary-darken-15` | ![#2a6496](https://ej2.syncfusion.com/download/documentation/svg/2a6496.svg) `#2a6496` | ![#00408a](./images/bootstrap-dark/00408a.png) `#00408a` |
| `$brand-primary-darken-25` | ![#1f496e](https://ej2.syncfusion.com/download/documentation/svg/1f496e.svg) `#1f496e` | ![#002957](./images/bootstrap-dark/002957.png) `#002957` |
| `$brand-primary-darken-35` | ![#142f46](https://ej2.syncfusion.com/download/documentation/svg/142f46.svg) `#142f46` | ![#001124](./images/bootstrap-dark/001124.png) `#001124` |
| `$brand-primary-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$grey-base` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#1a1a1a](https://ej2.syncfusion.com/download/documentation/svg/1a1a1a.svg) `#1a1a1a` |
| `$grey-darker` | ![#222222](https://ej2.syncfusion.com/download/documentation/svg/222222.svg) `#222222` | ![#131313](./images/bootstrap-dark/131313.png) `#131313` |
| `$grey-dark` | ![#333333](https://ej2.syncfusion.com/download/documentation/svg/333333.svg) `#333333` | ![#2a2a2a](./images/bootstrap-dark/2a2a2a.png) `#2a2a2a` |
| `$grey` | ![#555555](https://ej2.syncfusion.com/download/documentation/svg/555555.svg) `#555555` | ![#313131](./images/bootstrap-dark/313131.png) `#313131` |
| `$grey-light` | ![#777777](https://ej2.syncfusion.com/download/documentation/svg/777777.svg) `#777777` | ![#393939](./images/bootstrap-dark/393939.png) `#393939` |
| `$grey-44` | ![#444444](https://ej2.syncfusion.com/download/documentation/svg/444444.svg) `#444444` | ![#414141](./images/bootstrap-dark/414141.png) `#414141` |
| `$grey-88` | ![#888888](https://ej2.syncfusion.com/download/documentation/svg/888888.svg) `#888888` | ![#484848](./images/bootstrap-dark/484848.png) `#484848` |
| `$grey-99` | ![#999999](https://ej2.syncfusion.com/download/documentation/svg/999999.svg) `#999999` | ![#505050](./images/bootstrap-dark/505050.png) `#505050` |
| `$grey-8c` | ![#8c8c8c](https://ej2.syncfusion.com/download/documentation/svg/8c8c8c.svg) `#8c8c8c` | ![#585858](./images/bootstrap-dark/585858.png) `#585858` |
| `$grey-ad` | ![#adadad](https://ej2.syncfusion.com/download/documentation/svg/adadad.svg) `#adadad` | ![#676767](./images/bootstrap-dark/676767.png) `#676767` |
| `$grey-dark-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#f0f0f0](./images/bootstrap-dark/f0f0f0.png) `#f0f0f0` |
| `$grey-white` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#6e6e6e](./images/bootstrap-dark/6e6e6e.png) `#6e6e6e` |
| `$grey-lighter` | ![#eeeeee](https://ej2.syncfusion.com/download/documentation/svg/eeeeee.svg) `#eeeeee` | ![#767676](https://ej2.syncfusion.com/download/documentation/svg/767676.svg) `#767676` |
| `$grey-f9` | ![#f9f9f9](https://ej2.syncfusion.com/download/documentation/svg/f9f9f9.svg) `#f9f9f9` | ![#7e7e7e](./images/bootstrap-dark/7e7e7e.png) `#7e7e7e` |
| `$grey-f8` | ![#f8f8f8](https://ej2.syncfusion.com/download/documentation/svg/f8f8f8.svg) `#f8f8f8` | ![#858585](./images/bootstrap-dark/858585.png) `#858585` |
| `$grey-f5` | ![#f5f5f5](https://ej2.syncfusion.com/download/documentation/svg/f5f5f5.svg) `#f5f5f5` | ![#8d8d8d](./images/bootstrap-dark/8d8d8d.png) `#8d8d8d` |
| `$grey-e6` | ![#e6e6e6](https://ej2.syncfusion.com/download/documentation/svg/e6e6e6.svg) `#e6e6e6` | ![#959595](./images/bootstrap-dark/959595.png) `#959595` |
| `$grey-dd` | ![#dddddd](https://ej2.syncfusion.com/download/documentation/svg/dddddd.svg) `#dddddd` | ![#9c9c9c](./images/bootstrap-dark/9c9c9c.png) `#9c9c9c` |
| `$grey-d4` | ![#d4d4d4](https://ej2.syncfusion.com/download/documentation/svg/d4d4d4.svg) `#d4d4d4` | ![#a4a4a4](./images/bootstrap-dark/a4a4a4.png) `#a4a4a4` |
| `$grey-cc` | ![#cccccc](https://ej2.syncfusion.com/download/documentation/svg/cccccc.svg) `#cccccc` | ![#acacac](./images/bootstrap-dark/acacac.png) `#acacac` |
| `$grey-light-font` | ![#333333](https://ej2.syncfusion.com/download/documentation/svg/333333.svg) `#333333` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$brand-success` | ![#5cb85c](https://ej2.syncfusion.com/download/documentation/svg/5cb85c.svg) `#5cb85c` | ![#48b14c](./images/bootstrap-dark/48b14c.png) `#48b14c` |
| `$brand-success-dark` | ![#3c763d](https://ej2.syncfusion.com/download/documentation/svg/3c763d.svg) `#3c763d` | ![#358238](./images/bootstrap-dark/358238.png) `#358238` |
| `$brand-info` | ![#5bc0de](https://ej2.syncfusion.com/download/documentation/svg/5bc0de.svg) `#5bc0de` | ![#2aaac0](./images/bootstrap-dark/2aaac0.png) `#2aaac0` |
| `$brand-info-dark` | ![#31708f](https://ej2.syncfusion.com/download/documentation/svg/31708f.svg) `#31708f` | ![#208090](./images/bootstrap-dark/208090.png) `#208090` |
| `$brand-warning` | ![#f0ad4e](https://ej2.syncfusion.com/download/documentation/svg/f0ad4e.svg) `#f0ad4e` | ![#fac168](./images/bootstrap-dark/fac168.png) `#fac168` |
| `$brand-warning-dark` | ![#8a6d3b](https://ej2.syncfusion.com/download/documentation/svg/8a6d3b.svg) `#8a6d3b` | ![#f9ad37](./images/bootstrap-dark/f9ad37.png) `#f9ad37` |
| `$brand-danger` | ![#d9534f](https://ej2.syncfusion.com/download/documentation/svg/d9534f.svg) `#d9534f` | ![#d44f4f](./images/bootstrap-dark/d44f4f.png) `#d44f4f` |
| `$brand-danger-dark` | ![#a94442](https://ej2.syncfusion.com/download/documentation/svg/a94442.svg) `#a94442` | ![#c12f2f](./images/bootstrap-dark/c12f2f.png) `#c12f2f` |
| `$brand-success-light` | ![#dff0d8](https://ej2.syncfusion.com/download/documentation/svg/dff0d8.svg) `#dff0d8` | ![#dff0d8](https://ej2.syncfusion.com/download/documentation/svg/dff0d8.svg) `#dff0d8` |
| `$brand-info-light` | ![#d9edf7](https://ej2.syncfusion.com/download/documentation/svg/d9edf7.svg) `#d9edf7` | ![#d9edf7](https://ej2.syncfusion.com/download/documentation/svg/d9edf7.svg) `#d9edf7` |
| `$brand-warning-light` | ![#fcf8e3](https://ej2.syncfusion.com/download/documentation/svg/fcf8e3.svg) `#fcf8e3` | ![#fcf8e3](https://ej2.syncfusion.com/download/documentation/svg/fcf8e3.svg) `#fcf8e3` |
| `$brand-danger-light` | ![#f2dede](https://ej2.syncfusion.com/download/documentation/svg/f2dede.svg) `#f2dede` | ![#f2dede](https://ej2.syncfusion.com/download/documentation/svg/f2dede.svg) `#f2dede` |
| `$input-border-focus` | ![#66afe9](https://ej2.syncfusion.com/download/documentation/svg/66afe9.svg) `#66afe9` | ![#104888](./images/bootstrap-dark/104888.png) `#104888` |
| `$brand-success-font` | ![#3c763d](https://ej2.syncfusion.com/download/documentation/svg/3c763d.svg) `#3c763d` | ![#2f7432](./images/bootstrap-dark/2f7432.png) `#2f7432` |
| `$brand-info-font` | ![#31708f](https://ej2.syncfusion.com/download/documentation/svg/31708f.svg) `#31708f` | ![#1a6c7a](./images/bootstrap-dark/1a6c7a.png) `#1a6c7a` |
| `$brand-warning-font` | ![#8a6d3b](https://ej2.syncfusion.com/download/documentation/svg/8a6d3b.svg) `#8a6d3b` | ![#9d6106](./images/bootstrap-dark/9d6106.png) `#9d6106` |
| `$brand-danger-font` |![#a94442](https://ej2.syncfusion.com/download/documentation/svg/a94442.svg) `#a94442` | ![#ac2a2a](./images/bootstrap-dark/ac2a2a.png) `#ac2a2a` |
| `$base-font` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000` |

### Google's Material

| Name | Value (Default Theme) | Value (Dark Theme) |
| ------------- | ------------- | ------------- |
| `$accent` | ![#e3165b](https://ej2.syncfusion.com/download/documentation/svg/e3165b.svg) `#e3165b` | ![#00b0ff](./images/material-dark/00b0ff.png) `#00b0ff` |
| `$accent-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000` |
| `$primary` | ![#3f51b5](https://ej2.syncfusion.com/download/documentation/svg/3f51b5.svg) `#3f51b5` | ![#3f51b5](https://ej2.syncfusion.com/download/documentation/svg/3f51b5.svg) `#3f51b5` |
| `$primary-50` | ![#e8eaf6](https://ej2.syncfusion.com/download/documentation/svg/e8eaf6.svg) `#e8eaf6` | ![#e8eaf6](https://ej2.syncfusion.com/download/documentation/svg/e8eaf6.svg) `#e8eaf6` |
| `$primary-100` | ![#c5cae9](https://ej2.syncfusion.com/download/documentation/svg/c5cae9.svg) `#c5cae9` | ![#c5cae9](https://ej2.syncfusion.com/download/documentation/svg/c5cae9.svg) `#c5cae9` |
| `$primary-200` | ![#9fa8da](https://ej2.syncfusion.com/download/documentation/svg/9fa8da.svg) `#9fa8da` | ![#9fa8da](https://ej2.syncfusion.com/download/documentation/svg/9fa8da.svg) `#9fa8da` |
| `$primary-300` | ![#7986cb](https://ej2.syncfusion.com/download/documentation/svg/7986cb.svg) `#7986cb` | ![#7986cb](https://ej2.syncfusion.com/download/documentation/svg/7986cb.svg) `#7986cb` |
| `$primary-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$primary-50-font` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000000` |
| `$primary-100-font` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000000` |
| `$primary-200-font` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000000` |
| `$primary-300-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#ffffff` |
| `$grey-white` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$grey-black` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000` |
| `$grey-50` | ![#fafafa](https://ej2.syncfusion.com/download/documentation/svg/fafafa.svg) `#fafafa` | ![#fafafa](https://ej2.syncfusion.com/download/documentation/svg/fafafa.svg) `#fafafa` |
| `$grey-100` | ![#f5f5f5](https://ej2.syncfusion.com/download/documentation/svg/f5f5f5.svg) `#f5f5f5` | ![#f5f5f5](https://ej2.syncfusion.com/download/documentation/svg/f5f5f5.svg) `#f5f5f5` |
| `$grey-200` | ![#eeeeee](https://ej2.syncfusion.com/download/documentation/svg/eeeeee.svg) `#eeeeee` | ![#eee](https://ej2.syncfusion.com/download/documentation/svg/eeeeee.svg) `#eee` |
| `$grey-300` | ![#e0e0e0](https://ej2.syncfusion.com/download/documentation/svg/e0e0e0.svg) `#e0e0e0` | ![#e0e0e0](https://ej2.syncfusion.com/download/documentation/svg/e0e0e0.svg) `#e0e0e0` |
| `$grey-400` | ![#bdbdbd](https://ej2.syncfusion.com/download/documentation/svg/bdbdbd.svg) `#bdbdbd` | ![#bdbdbd](https://ej2.syncfusion.com/download/documentation/svg/bdbdbd.svg) `#bdbdbd` |
| `$grey-500` | ![#9e9e9e](https://ej2.syncfusion.com/download/documentation/svg/9e9e9e.svg) `#9e9e9e` | ![#9e9e9e](https://ej2.syncfusion.com/download/documentation/svg/9e9e9e.svg) `#9e9e9e` |
| `$grey-600` | ![#757575](https://ej2.syncfusion.com/download/documentation/svg/757575.svg) `#757575` | ![#757575](https://ej2.syncfusion.com/download/documentation/svg/757575.svg) `#757575` |
| `$grey-700` | ![#616161](https://ej2.syncfusion.com/download/documentation/svg/616161.svg) `#616161` | ![#616161](https://ej2.syncfusion.com/download/documentation/svg/616161.svg) `#616161` |
| `$grey-800` | ![#424242](https://ej2.syncfusion.com/download/documentation/svg/424242.svg) `#424242` | ![#424242](https://ej2.syncfusion.com/download/documentation/svg/424242.svg) `#424242` |
| `$grey-900` | ![#212121](https://ej2.syncfusion.com/download/documentation/svg/212121.svg) `#212121` | ![#212121](https://ej2.syncfusion.com/download/documentation/svg/212121.svg) `#212121` |
| `$grey-dark` | ![#303030](https://ej2.syncfusion.com/download/documentation/svg/303030.svg) `#303030` | ![#303030](https://ej2.syncfusion.com/download/documentation/svg/303030.svg) `#303030` |
| `$grey-light-font` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000` |
| `$grey-dark-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$base-font` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000` |
| `$error-font` | ![#f44336](https://ej2.syncfusion.com/download/documentation/svg/f44336.svg) `#f44336` | ![#f44336](https://ej2.syncfusion.com/download/documentation/svg/f44336.svg) `#f44336` |

### Microsoft Office’s Fabric

| Name | Value (Default Theme) | Value (Dark Theme) |
| ------------- | ------------- | ------------- |
| `$theme-primary` | ![#0078d7](https://ej2.syncfusion.com/download/documentation/svg/f44336.svg) `#0078d7` | ![#0074cc](./images/fabric-dark/0074cc.png) `#0074cc` |
| `$theme-dark-alt` | ![#006fc7](https://ej2.syncfusion.com/download/documentation/svg/006fc7.svg) `darken($theme-primary, 3%)` | ![#006bbd](./images/fabric-dark/006bbd.png) `006bbd` |
| `$theme-dark` | ![#005ba3](https://ej2.syncfusion.com/download/documentation/svg/005ba3.svg) `darken($theme-primary, 10%)` | ![#0063ad](./images/fabric-dark/0063ad.png) `0063ad` |
| `$theme-darker` | ![#00457a](https://ej2.syncfusion.com/download/documentation/svg/00457a.svg) `darken($theme-primary, 18%)` | ![#005799](./images/fabric-dark/005799.png) `005799` |
| `$theme-secondary` | ![#0081e5](https://ej2.syncfusion.com/download/documentation/svg/0081e5.svg) `lighten($theme-primary, 3%)` | ![#007ddb](./images/fabric-dark/007ddb.png) `007ddb` |
| `$theme-tertiary` | ![#42acff](https://ej2.syncfusion.com/download/documentation/svg/42acff.svg) `lighten($theme-primary, 21%)` | ![#38a9ff](./images/fabric-dark/38a9ff.png) `38a9ff` |
| `$theme-light` | ![#b7e0ff](https://ej2.syncfusion.com/download/documentation/svg/b7e0ff.svg) `lighten($theme-primary, 44%)` | ![#addcff](./images/fabric-dark/addcff.png) `addcff` |
| `$theme-lighter` | ![#d1ebff](https://ej2.syncfusion.com/download/documentation/svg/d1ebff.svg) `lighten($theme-primary, 49%)` | ![#c7e7ff](./images/fabric-dark/c7e7ff.png) `c7e7ff` |
| `$theme-lighter-alt` | ![#aliceblue](https://ej2.syncfusion.com/download/documentation/svg/aliceblue.svg) `lighten($theme-primary, 55%)` | ![#e6f4ff](./images/fabric-dark/e6f4ff.png) `e6f4ff` |
| `$neutral-white` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#201f1f](./images/fabric-dark/201f1f.png) `#201f1f` |
| `$neutral-lighter-alt` | ![#f8f8f8](https://ej2.syncfusion.com/download/documentation/svg/f8f8f8.svg) `#f8f8f8` | ![#282727](./images/fabric-dark/282727.png) `#282727` |
| `$neutral-lighter` | ![#f4f4f4](https://ej2.syncfusion.com/download/documentation/svg/f4f4f4.svg) `#f4f4f4` | ![#333232](./images/fabric-dark/333232.png) `#333232` |
| `$neutral-light` | ![#eaeaea](https://ej2.syncfusion.com/download/documentation/svg/eaeaea.svg) `#eaeaea` | ![#414040](./images/fabric-dark/414040.png) `#414040` |
| `$neutral-quintenaryalt` | ![#dadada](https://ej2.syncfusion.com/download/documentation/svg/dadada.svg) `#dadada` | ![#4a4848](./images/fabric-dark/4a4848.png) `#4a4848` |
| `$neutral-quintenary` | ![#d0d0d0](https://ej2.syncfusion.com/download/documentation/svg/d0d0d0.svg) `#d0d0d0` | ![#514f4f](./images/fabric-dark/514f4f.png) `#514f4f` |
| `$neutral-tertiary-alt` | ![#c8c8c8](https://ej2.syncfusion.com/download/documentation/svg/c8c8c8.svg) `#c8c8c8` | ![#6f6c6c](./images/fabric-dark/6f6c6c.png) `#6f6c6c` |
| `$neutral-tertiary` | ![#a6a6a6](https://ej2.syncfusion.com/download/documentation/svg/a6a6a6.svg) `#a6a6a6` | ![#9a9a9a](./images/fabric-dark/9a9a9a.png) `#9a9a9a` |
| `$neutral-secondary-alt` | ![#767676](https://ej2.syncfusion.com/download/documentation/svg/767676.svg) `#767676` | ![#c8c8c8](https://ej2.syncfusion.com/download/documentation/svg/c8c8c8.svg) `#c8c8c8` |
| `$neutral-secondary` | ![#666666](https://ej2.syncfusion.com/download/documentation/svg/666666.svg) `#666666` | ![#dadada](https://ej2.syncfusion.com/download/documentation/svg/dadada.svg) `#dadada` |
| `$neutral-primary` | ![#333333](https://ej2.syncfusion.com/download/documentation/svg/333333.svg) `#333333` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$neutral-dark` | ![#212121](https://ej2.syncfusion.com/download/documentation/svg/212121.svg) `#212121` | ![#f4f4f4](https://ej2.syncfusion.com/download/documentation/svg/f4f4f4.svg) `#f4f4f4` |
| `$neutral-black` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#f8f8f8](https://ej2.syncfusion.com/download/documentation/svg/f8f8f8.svg) `#f8f8f8` |
| `$alert-bg` | ![#deecf9](https://ej2.syncfusion.com/download/documentation/svg/deecf9.svg) `#deecf9` | ![#bf7500](./images/fabric-dark/bf7500.png) `#bf7500` |
| `$error-bg` | ![#fde7e9](https://ej2.syncfusion.com/download/documentation/svg/fde7e9.svg) `#fde7e9` | ![#cd2a19](./images/fabric-dark/cd2a19.png) `#cd2a19` |
| `$success-bg` | ![#dff6dd](https://ej2.syncfusion.com/download/documentation/svg/dff6dd.svg) `#dff6dd` | ![#37844d](./images/fabric-dark/37844d.png) `#37844d` |
| `$theme-dark-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$theme-primary-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$theme-light-font` | ![#333333](https://ej2.syncfusion.com/download/documentation/svg/333333.svg) `#333333` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000` |
| `$neutral-light-font` | ![#333333](https://ej2.syncfusion.com/download/documentation/svg/333333.svg) `#333333` | ![#dadada](https://ej2.syncfusion.com/download/documentation/svg/dadada.svg) `#dadada` |
| `$neutral-light-fontalt` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$grey-dark-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` | ![#000](https://ej2.syncfusion.com/download/documentation/svg/000.svg) `#000` |
| `$base-font` | ![#333333](https://ej2.syncfusion.com/download/documentation/svg/333333.svg) `#333333` | ![#dadada](https://ej2.syncfusion.com/download/documentation/svg/dadada.svg) `#dadada` |
| `$message-font` | ![#333333](https://ej2.syncfusion.com/download/documentation/svg/333333.svg) `#333333` | ![#fff](https://ej2.syncfusion.com/download/documentation/svg/fff.svg) `#fff` |
| `$alert-font` | ![#d83b01](https://ej2.syncfusion.com/download/documentation/svg/d83b01.svg) `#d83b01` | ![#ff9d48](./images/fabric-dark/ff9d48.png) `#ff9d48` |
| `$error-font` | ![#a80000](https://ej2.syncfusion.com/download/documentation/svg/a80000.svg) `#a80000` | ![#ff5f5f](./images/fabric-dark/ff5f5f.png) `#ff5f5f` |
| `$success-font` | ![#107c10](https://ej2.syncfusion.com/download/documentation/svg/107c10.svg) `#107c10` | ![#8eff8d](./images/fabric-dark/8eff8d.png) `#8eff8d` |

### High Contrast

| Name | Value |
| ------------- | ------------- |
| `$selection-bg` | ![#ffd939](https://ej2.syncfusion.com/download/documentation/svg/ffd939.svg) `#ffd939` |
| `$selection-font` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` |
| `$selection-border` | ![#ffd939](https://ej2.syncfusion.com/download/documentation/svg/ffd939.svg) `#ffd939` |
| `$hover-bg` | ![#685708](https://ej2.syncfusion.com/download/documentation/svg/685708.svg) `#685708` |
| `$hover-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` |
| `$hover-border` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` |
| `$border-default` | ![#969696](https://ej2.syncfusion.com/download/documentation/svg/969696.svg) `#969696` |
| `$border-alt` | ![#757575](https://ej2.syncfusion.com/download/documentation/svg/757575.svg) `#757575` |
| `$border-fg` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` |
| `$border-fg-alt` | ![#ffd939](https://ej2.syncfusion.com/download/documentation/svg/ffd939.svg) `#ffd939` |
| `$bg-base-0` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` |
| `$bg-base-5` | ![#0d0d0d](https://ej2.syncfusion.com/download/documentation/svg/0d0d0d.svg) `#0d0d0d` |
| `$bg-base-10` | ![#1a1a1a](https://ej2.syncfusion.com/download/documentation/svg/1a1a1a.svg) `#1a1a1a` |
| `$bg-base-15` | ![#262626](https://ej2.syncfusion.com/download/documentation/svg/262626.svg) `#262626` |
| `$bg-base-20` | ![#333333](https://ej2.syncfusion.com/download/documentation/svg/333333.svg) `#333333` |
| `$bg-base-75` | ![#bfbfbf](https://ej2.syncfusion.com/download/documentation/svg/bfbfbf.svg) `#bfbfbf` |
| `$bg-base-100` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` |
| `$header-font` | ![#ffd939](https://ej2.syncfusion.com/download/documentation/svg/ffd939.svg) `#ffd939` |
| `$header-font-alt` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` |
| `$content-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` |
| `$content-font-alt` | ![#969696](https://ej2.syncfusion.com/download/documentation/svg/969696.svg) `#969696` |
| `$link` | ![#8a8aff](https://ej2.syncfusion.com/download/documentation/svg/8a8aff.svg) `#8a8aff` |
| `$invert-font` | ![#000000](https://ej2.syncfusion.com/download/documentation/svg/000000.svg) `#000000` |
| `$success-bg` | ![#166600](https://ej2.syncfusion.com/download/documentation/svg/166600.svg) `#166600` |
| `$error-bg` | ![#b30900](https://ej2.syncfusion.com/download/documentation/svg/b30900.svg) `#b30900` |
| `$message-font` | ![#ffffff](https://ej2.syncfusion.com/download/documentation/svg/ffffff.svg) `#ffffff` |
| `$alert-bg` | ![#944000](https://ej2.syncfusion.com/download/documentation/svg/944000.svg) `#944000` |
| `$info-bg` | ![#0056b3](https://ej2.syncfusion.com/download/documentation/svg/0056b3.svg) `#0056b3` |
| `$success-alt` | ![#2bc700](https://ej2.syncfusion.com/download/documentation/svg/2bc700.svg) `#2bc700` |
| `$error-alt` | ![#ff6161](https://ej2.syncfusion.com/download/documentation/svg/ff6161.svg) `#ff6161` |
| `$alert-alt` | ![#ff7d1a](https://ej2.syncfusion.com/download/documentation/svg/ff7d1a.svg) `#ff7d1a` |
| `$info-alt` | ![#66b0ff](https://ej2.syncfusion.com/download/documentation/svg/66b0ff.svg) `#66b0ff` |
| `$disable` | ![#757575](https://ej2.syncfusion.com/download/documentation/svg/757575.svg) `#757575` |
