# How to Configure Syncfusion Blazor Client Resources in Production Environment

* The Syncfusion Blazor suit maintains the built-in script resources (interop scripts) by default for the development environment. So, there is no need to include script reference in the application end.

* However, we highly recommend to add the Syncfusion Blazor init interop script or custom interop script in the application end for the production environment.

## Adding Syncfusion Blazor init interop script in the production application

* Set `DisableScriptManager` as true to the `AddSyncfusionBlazor` service in the `~/Startup.cs` file for Blazor server app or `~/Program.cs` file for Blazor WebAssembly app.

    **Blazor Server App (~/Startup.cs)**
    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddRazorPages();
        services.AddServerSideBlazor();

        // Set DisableScriptManager as true to load init script manually in the application end
        services.AddSyncfusionBlazor(true);

        services.AddSingleton<WeatherForecastService>();
    }
    ```

    **Blazor WebAssembly App (~/Program.cs)**
    ```csharp
    public static async Task Main(string[] args)
    {
        var builder = WebAssemblyHostBuilder.CreateDefault(args)    ;
        ....
        ....

        // Set DisableScriptManager as true to load init script manually in the application end
        builder.Services.AddSyncfusionBlazor(true);

        await builder.Build().RunAsync();
    }
    ```

* Add Syncfusion Blazor resources manually in the `~/Pages/_Host.cshtml` file for Blazor server app or `~/wwwroot/index.html` file for Blazor WebAssembly app.

    ```html
    <head>
        ....
        ....
        <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
        <script src="_content/Syncfusion.Blazor/scripts/syncfusion-blazor.min.js" type="text/javascript"></script>
    </head>
    ```
* Now, publish the application with the production environment in the server.

## Creating custom resources for Syncfusion Blazor UI Components

* [CRG](https://blazor.syncfusion.com/crg) is an online webtool. You can create custom interop scripts and styles for a specific set of components from this tool. Refer to [here](https://blazor.syncfusion.com/documentation/common/custom-resource-generator/) for more details about CRG.

* Disable built-in scripts and add the custom scripts manually in the application by referring [this](https://blazor.syncfusion.com/documentation/common/custom-resource-generator/#how-to-use-custom-resources-in-the-blazor-application) documentation.

* Now, publish the application with the production environment in the server.