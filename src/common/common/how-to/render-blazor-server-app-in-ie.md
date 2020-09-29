# How to Render the Blazor Server Application in IE Web Browser

## Blazor WebAssembly App

†Microsoft Internet Explorer doesn't support with `WebAssembly`. So, Blazor WebAssembly application does not support with Internet Explorer.

## Blazor Server App

†Microsoft Internet Explorer supports `Blazor Server` app with additional polyfills. Find the following steps to add the polyfills in the Blazor server application.

## Create a Blazor Server Application

1. Create a Blazor server Application using [Blazor Server](../../getting-started/server-side-blazor) documentation.

2. Add the style file references and [`github.com/Daddoon/Blazor.Polyfill`](https://github.com/Daddoon/Blazor.Polyfill) in the `<head>` element of the **~/Pages/_Host.cshtml** page.

    ```html
    <head>

    .....
    .....

    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
    </head>

    ```
    > This [polyfill](https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js) is required to configure in Blazor server application for IE 11 support.

3. Run the Application, The Syncfusion Blazor Component will render in the IE 11 web browser.

    ![output](../../getting-started/images/browser-output.png)
