# How to customize the font size and color in Syncfusion Blazor components

## Install Webcompiler

Install the Webcompiler to compile the `scss` files in the Blazor Applications.

## Steps to install the Webcompiler in Visual Studio 2019**

1. Open the Visual Studio 2019 and click the **Exensions** in the visual studio toolbar.

    ![Extension](../images/extensions.png)

2. Download and install the **Web Compiler** in the visual studio 2019.

    ![WebCompiler](../images/webcompiler.png)

## Create a Blazor Server Application in Visual Studio 2019

1. Create a Blazor server application by referring [Blazor Server](../../getting-started/vs-blazor-server) documentation.

2. Install the Syncfusion `node_modules` in this application using this command.

    ```cmd

    npm install @syncfusion/ej2

    ```

3. Create a `scss` file in root folder and provide the variables to override as shown below.

    ``` scss

    $calendar-normal-max-width: 362px !default;
    $calendar-normal-min-width: 256px !default;
    $primary: green !default;

    @import 'ej2-base/styles/bootstrap4.scss';
    @import 'ej2-buttons/styles/bootstrap4.scss';
    @import 'ej2-calendars/styles/bootstrap4.scss';

    ```

4. Right click the `scss` file and click the Web Compiler to compile the file.

    ![compile](../images/compile.png)

5. The **compilerconfig.json** file is created. Then provide the location of the compiled css file and include path like the following code snippet.

    ```json
        {
            "outputFile": "wwwroot/Custom.css",
            "inputFile": "styles/Custom.scss"
        }

        {
            "sass": {
            "autoPrefix": "",
            "includePath": "./@syncfusion",
    ```

6. The `Scss` file has been compiled to the css file. Then, add this css file to the `<head>` element of the **~/Pages/_Host.cshtml** page.

    ```html
    <head>

    .....
    .....

    <link href="~/Custom.min.css" rel="stylesheet" />
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ej2.min.js"></script>
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ejs.interop.min.js"></script>
    <head>

    ```

    > **Note:** For production purpose and minimal requirement, Syncfusion provides an option to generate scripts and styles of selective control by using the Custom Resource Generator (CRG) web tool. Refer to this [link](https://crg.syncfusion.com/) for more details on CRG.

7. Run the application. The styles are applied in our Blazor component.

    ![sample](../images/sample.png)