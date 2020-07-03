# Deployment

## CDN

The CDN links are published individually for all the scripts and style sheets of Syncfusion JavaScript UI controls. The below files are hosted in the CDN links for each Syncfusion npm packages.

1. UMD (Universal Module Definition) Files
2. Global (ES5) Files
3. CSS Files

The latest minified versions of UMD (Universal Module Definition), Global (ES5) and CSS files for each npm package are available in the below CDN format.

* **`https://cdn.syncfusion.com/ej2/{PACKAGE-NAME}/dist/{PACKAGE-NAME}.umd.min.js`**
* **`https://cdn.syncfusion.com/ej2/{PACKAGE-NAME}/dist/global/{PACKAGE-NAME}.min.js`**
* **`https://cdn.syncfusion.com/ej2/{PACKAGE-NAME}/styles/{THEME-NAME}.css`**

For example,

* [https://cdn.syncfusion.com/ej2/ej2-grids/dist/ej2-grids.umd.min.js](https://cdn.syncfusion.com/ej2/ej2-grids/dist/ej2-grids.umd.min.js)
* [https://cdn.syncfusion.com/ej2/ej2-grids/dist/global/ej2-grids.min.js](https://cdn.syncfusion.com/ej2/ej2-grids/dist/global/ej2-grids.min.js)
* [https://cdn.syncfusion.com/ej2/ej2-grids/styles/material.css](https://cdn.syncfusion.com/ej2/ej2-grids/styles/material.css)

The Syncfusion npm package released version files are also available in the below CDN format.

* **`https://cdn.syncfusion.com/ej2/{VERSION}/{PACKAGE-NAME}/dist/{PACKAGE-NAME}.umd.min.js`**
* **`https://cdn.syncfusion.com/ej2/{VERSION}/{PACKAGE-NAME}/dist/global/{PACKAGE-NAME}.min.js`**
* **`https://cdn.syncfusion.com/ej2/{VERSION}/{PACKAGE-NAME}/styles/{THEME-NAME}.css`**

For example

* [https://cdn.syncfusion.com/ej2/16.3.21/ej2-grids/dist/ej2-grids.umd.min.js](https://cdn.syncfusion.com/ej2/16.3.21/ej2-grids/dist/ej2-grids.umd.min.js)
* [https://cdn.syncfusion.com/ej2/16.3.21/ej2-grids/dist/global/ej2-grids.min.js](https://cdn.syncfusion.com/ej2/16.3.21/ej2-grids/dist/global/ej2-grids.min.js)
* [https://cdn.syncfusion.com/ej2/16.3.21/ej2-grids/styles/material.css](https://cdn.syncfusion.com/ej2/16.3.21/ej2-grids/styles/material.css)

## NPM packages

The Syncfusion JavaScript (Essential JS 2) npm packages are published and available in public [npm](https://www.npmjs.com/search?q=scope:syncfusion) registry and it is available as an open source software.

### Anatomy of NPM packages

The Syncfusion JavaScript controls are published as npm packages. The below table explains the purpose of each file available in the npm package.

|    Files                                                                  |    Purpose                                                                                                                                                                                                                                                                                   |
|---------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `dist/es6`                                                               |    This folder contains the ES6 formatted JS file of   the package.                                                                                                   |
|    `dist/<package-name>.umd.min.js`   `dist/<package-name>.umd.min.js.map`              |        For applications using AMD or Common JS based module loader can utilize these files. This file can be used to load in [`System.js`](https://github.com/systemjs/systemjs) or [`RequireJS`](https://requirejs.org/).                                                                                                                                                                                           |
|    `dist/global/<package-name>.min.js`   `dist/global/<package-name>.min.js.map`        |    The global folder contains the ES5 script files for creating and manipulating Syncfusion JavaScript controls using a global variable name `window.ej`. All Syncfusion JavaScript controls are available within the `window.ej` variable. This file can be used directly in the script tag without using any module loaders.    |
|    `src/`                                                                   |    This folder contains the script files in ES6 format.                                                                                                                                                         |
|    `styles/<theme name>.css`   `styles/<theme name>.scss`                     |    This folder contains the CSS and SCSS files of the   package.                                                                                                                                                                                                                             ||

## Bundling and Tree Shaking

The Syncfusion JavaScript (Essential JS 2) packages has support for bundling and tree-shaking the script files. Using bundling you can combine the JavaScript modules in a single file. Using Tree Shaking, you can exclude the unused script modules for production bundle.

### Webpack and Module Injection

Large components provides the Module Injection for their features. For example, Grid control has some features like Sorting, Paging, Filtering, etc., To use these features in Grid control we need to require the respective module from the package and other features no need to be required when that is not used. So, the Module Injection helps to remove bunch of unused codes in the application. This will reduce the file size on production.

#### Example to Use Module Injection in Grid control

1. Clone Syncfusion JavaScript (Essential JS 2) seed application from [GitHub](https://github.com/syncfusion/ej2-typescript-seed.git)

    ```sh
    git clone https://github.com/syncfusion/ej2-typescript-seed.git webpack-demo
    cd webpack-demo
    npm install
    ```

2. This application is pre-configured with Webpack. The `webpack.config.js` file in the root of the application can be customized based on the requirement.

3. Add the below code snippets in the `~/src/app/index.ts` file.

    ```typescript
    import { Grid, Sort } from '@syncfusion/ej2-grids';
    import { data } from './datasource.ts';

    Grid.Inject(Sort);

    let grid: Grid = new Grid({
        dataSource: data,
        allowSorting: true,
        columns: [
            { field: 'OrderID', headerText: 'Order ID', textAlign: 'Right', width: 120 },
            { field: 'CustomerID', headerText: 'Customer ID', width: 150 },
            { field: 'ShipCity', headerText: 'Ship City', width: 150 },
            { field: 'ShipName', headerText: 'Ship Name', width: 150 }
        ],
        height: 315
    });
    grid.appendTo('#Grid');
    ```
4. Create a `~/src/app/datasource.ts` file and add the below content for Grid data-source.

    ```typescript
    export let data: Object[] = [
        {
            OrderID: 10248, CustomerID: 'VINET', EmployeeID: 5, OrderDate: new Date(8364186e5),
            ShipName: 'Vins et alcools Chevalier', ShipCity: 'Reims', ShipAddress: '59 rue de l Abbaye',
            ShipRegion: 'CJ', ShipPostalCode: '51100', ShipCountry: 'France', Freight: 32.38, Verified: !0
        },
        {
            OrderID: 10249, CustomerID: 'TOMSP', EmployeeID: 6, OrderDate: new Date(836505e6),
            ShipName: 'Toms Spezialitäten', ShipCity: 'Münster', ShipAddress: 'Luisenstr. 48',
            ShipRegion: 'CJ', ShipPostalCode: '44087', ShipCountry: 'Germany', Freight: 11.61, Verified: !1
        },
        {
            OrderID: 10250, CustomerID: 'HANAR', EmployeeID: 4, OrderDate: new Date(8367642e5),
            ShipName: 'Hanari Carnes', ShipCity: 'Rio de Janeiro', ShipAddress: 'Rua do Paço, 67',
            ShipRegion: 'RJ', ShipPostalCode: '05454-876', ShipCountry: 'Brazil', Freight: 65.83, Verified: !0
        }
    ];
    ```

5. Replace the below code snippet to the `<body>` element in `~/src/app/index.html` file.

    ```html
    <body>
        <div style="margin: 50px;">
            <div id='Grid'></div>
        </div>

        <script src="index.js" type="text/javascript"></script>
    </body>
    ```

6. Open the command prompt from the application folder and run the command line `npm start`. After Webpack compilation, `index.js` file will be created for the necessary codes of the application and the unused modules are excluded in the Webpack bundle.

### Tree Shaking in Webpack

1. Clone Syncfusion JavaScript (Essential JS 2) seed application from the GitHub repository and navigate to the cloned folder.

    ```sh
    git clone https://github.com/syncfusion/ej2-typescript-seed.git webpack-demo
    cd webpack-demo
    npm install
    ```

2. Edit the `~/webpack.config.js` file with the below code snippet.

    ```javascript
    var webpack = require('webpack');

    module.exports = {
        mode: 'development',
        entry: {
            'src/app/index': './src/app/index.ts'
        },
        output: {
            filename: '[name].js'
        },
        module: {
            rules: [{
                loader: 'ts-loader',
                exclude: /node_modules/,
            }]
        },
        resolve: {
            extensions: [".ts", ".js"]
        },
    }
    ```

3. Run the command line `npm start` to run the application.

**Note:** This will bundle the source file as per the configuration specified in `webpack.config.js`. Providing `mode` configuration option tells Webpack to use its built-in optimizations accordingly. If not set Webpack sets `Production` as default value or `mode`.