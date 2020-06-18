# How to troubleshoot server and client exceptions

## Runtime exceptions

* **InvalidOperationException: Cannot provide a value for property 'SyncfusionService' on type 'Syncfusion.EJ2.Blazor.Namespace.Component'**

    You may see the below runtime exception while running the application first time.

    > Error: **InvalidOperationException:** Cannot provide a value for property 'SyncfusionService' on type 'Syncfusion.EJ2.Blazor.Namespace.Component'. There is no registered service of type 'Syncfusion.EJ2.Blazor.SyncfusionBlazorService'.

    **Cause:**

    This exception thrown, because you missed to register the `SyncfusionBlazorService` in `Startup.cs`.

    **Solution:**

    You can register the `SyncfusionBlazorService` in `Startup.cs` file to resolve the exception.

    ```csharp
    using Syncfusion.EJ2.Blazor;
    public class Startup
    {
        ....
        ....

        public void ConfigureServices(IServiceCollection services)
        {
            ....
            ....
            services.AddSyncfusionBlazor();
        }

        ....
        ....
    }
    ```

* **System.NullReferenceException: Object reference not set to an instance of an object**

    You may see the below exception while running the application in your production/server machine.

    > Error: **System.NullReferenceException:** Object reference not set to an instance of an object.
    > at `Syncfusion.EJ2.Blazor.SyncfusionBlazorService.GetContext()`
    > at `Syncfusion.EJ2.Blazor.BaseComponent.OnInitializedAsync()`
    > at `Syncfusion.EJ2.Blazor.Charts.EjsChart.OnInitializedAsync()`
    > at `Microsoft.AspNetCore.Components.ComponentBase.RunInitAndSetParametersAsync()`

    **Cause:**

    The production/hosting server machine may have outdated configuration like .NET Core SDK and .NET Core runtime hosting bundle.

    **Solution:**

    Update your dotnet sdk/hosting bundle with latest version in your production/hosting server machine.

    Install the latest sdk/hosting bundle from [here](https://dotnet.microsoft.com/download/dotnet-core/) in your hosting machine to resolve this.

* **The type name 'Shared' does not exist in the type 'SyncfusionBlazor'**

   You may see the below exception while running the Syncfusion blazor
   application.

    > Error: The type name 'Shared' does not exist in the type 'SyncfusionBlazor' SyncfusionBlazor `\SyncfusionBlazor\SyncfusionBlazor\obj\Debug\netcoreapp3.1\Razor\Shared\MainLayout.razor.g.cs`

   **Cause:**

    This issue occurred, if you are creating the application name as **SyncfusionBlazor**. The name **SyncfusionBlazor** is already registered in the Syncfusion service handling. So your application name and the internally used class name gets conflict.

   **Solution:**

   Try to use different application name, when you create the blazor application with Syncfusion Blazor components.

## Browser console errors

* **An unhandled exception has occurred. See browser dev tools for details**

    You may see the below exception at the bottom of the page.

    > Error: An unhandled exception has occurred. See browser dev tools for details

    **Cause:**

    There may be script error thrown in the JS Interop or client script source.

    **Solution:**

    Open the browser dev tool by pressing `F12` key and navigate to `Console` tab.

    Check the console error with the following topics to resolve the issue or report us the console error through our [support ticket](http://syncfusion.com/support).

* **Error: Microsoft.JSInterop.JSException: Could not find 'ejsInterop' in 'window'**

    You may see the below console error in the browser dev tool while using Syncfusion components in the Blazor application.

    > Error: Microsoft.JSInterop.JSException: Could not find 'ejsInterop' in 'window'.

    **Cause:**

    This console error thrown, because you missed to add the `ejs.interop.js` reference in your application.

    **Solution:**

    Add the below script reference in `~/Pages/_Host.cshtml` file for Blazor server app. If you are using Blazor WebAssembly app, then add the script reference in `~/wwwroot/index.html` file.

    ```html
    <head>
        ....
        ....

        <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ejs.interop.min.js"></script>
    </head>
    ```
