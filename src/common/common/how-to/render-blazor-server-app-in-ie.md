# How to Render the Blazor Server Application in IE Web Browser

## Blazor WebAssembly

†Microsoft Internet Explorer doesn't support `WebAssembly`. So, Blazor WebAssembly does not support with Internet Explorer.

## Blazor Server

†Microsoft Internet Explorer supports `Blazor Server` with additional polyfills. Find the following steps to add the polyfills in Blazor server application.

## Create a Blazor Server Application

1. Create a Blazor server Application using [Blazor Server](../../getting-started/vs-blazor-server) documentation.

2. Add the client resource file references and [`github.com/Daddoon/Blazor.Polyfill`](https://github.com/Daddoon/Blazor.Polyfill) in the `<head>` element of the **~/Pages/_Host.cshtml** page.

    ```html
    <head>

    .....
    .....

    <link href="https://cdn.syncfusion.com/ej2/{:version:}/material.css" rel="stylesheet" />
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ej2.min.js"></script>
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ejs.interop-ie.min.js"></script>
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
    </head>

    ```

    > **Note:** For production purpose and minimal requirement, Syncfusion provides an option to generate scripts and styles of selective control by using Custom Resource Generator (CRG) web tool. Refer this [link](https://crg.syncfusion.com/) for more details on CRG.
    >
    > Refer the `ejs.interop-ie.min.js` file instead of `ejs.interop.min.js` file to render the Blazor server application in IE web browser.

3. Run the Application, The Syncfusion Blazor Component will render in the IE web browser.

    ![output](../../getting-started/images/browser-output.png)
