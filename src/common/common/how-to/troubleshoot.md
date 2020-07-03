# How to troubleshoot server and client exceptions

## Runtime exceptions

* **InvalidOperationException: Cannot provide a value for property 'SyncfusionService' on type 'Syncfusion.Blazor.Namespace.Component'**

    You may see the below runtime exception while running the application for the first time.

    > Error: **InvalidOperationException:** Cannot provide a value for property 'SyncfusionService' on type 'Syncfusion.Blazor.Namespace.Component'. There is no registered service of type 'Syncfusion.Blazor.SyncfusionBlazorService'.

    **Cause:**

    This exception thrown because you missed registering the `SyncfusionBlazorService` in `Startup.cs`.

    **Solution:**

    You can register the `SyncfusionBlazorService` in `Startup.cs` file to resolve the exception.

    ```csharp
    using Syncfusion.Blazor;
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
    > at `Syncfusion.Blazor.SyncfusionBlazorService.GetContext()`
    > at `Syncfusion.Blazor.BaseComponent.OnInitializedAsync()`
    > at `Syncfusion.Blazor.Charts.SfChart.OnInitializedAsync()`
    > at `Microsoft.AspNetCore.Components.ComponentBase.RunInitAndSetParametersAsync()`

    **Cause:**

    The production/hosting server machine may have an outdated configuration like .NET Core SDK and .NET Core runtime hosting bundle.

    **Solution:**

    Update your dotnet SDK/hosting bundle with the latest version in your production/hosting server machine.

    Install the latest dotnet SDK/hosting bundle from [here](https://dotnet.microsoft.com/download/dotnet-core/) in your hosting machine to resolve this.

* **The type name 'Shared' does not exist in the type 'SyncfusionBlazor'**

   You may see the below exception while running the Syncfusion blazor
   application.

    > Error: The type name 'Shared' does not exist in the type 'SyncfusionBlazor' SyncfusionBlazor `\SyncfusionBlazor\SyncfusionBlazor\obj\Debug\netcoreapp3.1\Razor\Shared\MainLayout.razor.g.cs`

   **Cause:**

    This issue occurred, if you are creating the application name as **SyncfusionBlazor**. The name **SyncfusionBlazor** is already registered in the Syncfusion service handling. So your application name and the internally used class name gets conflict.

   **Solution:**

   Try to use a different application name, when you create the blazor application with Syncfusion Blazor components.

* **System.IO.FileLoadException: Could not load file or assembly 'System.Text.Json**

    You may get the below exception while running the Syncfusion blazor application.

    > Error: System.IO.FileLoadException: Could not load file or assembly 'System.Text.Json, Version=4.0.1.1, Culture=neutral PublicKeyToken=cc7b13ffcd2ddd51'. The located assembly's manifest definition does not match the assembly reference.

    **Cause:**

    You may have .NET Core SDK older than version 3.1.2, but Syncfusion Blazor components need the latest version of .NET Core SDK as stated in the [pre-requisite](https://blazor.syncfusion.com/documentation/getting-started/server-side-blazor/?#prerequisites) documentation.

    **Solution:**

    Check installed .NET Core SDK version and update to the latest version. You can also find/download the details of the latest .NET Core SDK version [here](https://dotnet.microsoft.com/download/dotnet-core/).

## Compile-time errors

* **The type or namespace name 'EJ2' does not exist in the namespace 'Syncfusion' (are you missing an assembly reference?)**

    You may see the below compile-time exception while running the application.

    > Error: The type or namespace name 'EJ2' does not exist in the namespace 'Syncfusion' (are you missing an assembly reference?)

    **Cause:**

    You may use deprecated namespace in the application with Syncfusion Blazor NuGet package version greater than or equal to 18.1.0.36.

    **Solution**

    The Syncfusion Blazor library has changed its namespace, NuGet package name, component name from v18.1.0.36. Refer this [documentation](./upgrade-syncfusion-components-to-18.1.0.36-version/#namespace-changes) to migrate your application with correct namespace. Example: `Syncfusion.EJ2.Blazor` is now modified as `Syncfusion.Blazor`.

* **Found markup element with unexpected name 'Ejs'. If this is intended to be a component, add a @using directive for its namespace**

    You may see the below compile-time exception while running the application.

    > Error: Found markup element with unexpected name 'Ejs'. If this is intended to be a component, add a @using directive for its namespace

    **Cause:**

    You may use the deprecated component name in the application with the Syncfusion Blazor NuGet package version greater than or equal to 18.1.0.36.

    **Solution**

    The Syncfusion Blazor library has changed its namespace, NuGet package name and component name from v18.1.0.36. Refer this [documentation](./upgrade-syncfusion-components-to-18.1.0.36-version/#component-name-changes) to migrate your application with correct component name. Example: `EjsGrid` is now modified as `SfGrid`.

## Browser console errors

* **An unhandled exception has occurred. See browser dev tools for details**

    You may see the below exception at the bottom of the page.

    > Error: An unhandled exception has occurred. See browser dev tools for details

    **Cause:**

    There may be script errors thrown in the JS Interop or client script source.

    **Solution:**

    Open the browser dev tool by pressing the `F12` key and navigate to the `Console` tab.

    Check the console error with the following topics to resolve the issue or report us the console error through our [support ticket](http://syncfusion.com/support).
