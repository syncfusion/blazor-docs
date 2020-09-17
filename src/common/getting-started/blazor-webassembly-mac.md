 <!-- markdownlint-disable MD024 -->

# Getting started with Syncfusion Blazor - WebAssembly App in Visual Studio for Mac

This article provides a step-by-step introduction to configure Syncfusion Blazor setup, build and run a simple Blazor WebAssembly application using [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/).

> **Note:** Starting with version 17.4.0.39 (2019 Volume 4), you need to include a valid license key (either paid or trial key) within your applications. Please refer to this [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#blazor) for more information.

## Prerequisites

* [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)
* [.NET Core SDK 3.1.8](https://dotnet.microsoft.com/download/dotnet-core/3.1)

> **Note:** .NET Core SDK 3.1.8 requires Visual Studio for Mac 8.7.6 or later.

## Create a Blazor WebAssembly project in Visual Studio for Mac

1. Choose **New** from the Visual Studio for Mac dashboard.

    ![new project in blazor](images/mac-new-project.png)

2. Select **Blazor WebAssembly App** from the template and click **Next** button.

    ![blazor template](images/mac-wasm-template.png)

3. Continue with **No Authentication** selection in Authentication and click **Next** button.

    ![blazor authentication](images/mac-wasm-authentication.png)

4. Now, the Blazor WebAssembly App project configuration window will popup. Click **Create** button to create a new project after filling Project name.

    ![blazor project configuration](images/mac-wasm-project-config.png)

## Importing Syncfusion Blazor component in the application

1. Now, install **Syncfusion.Blazor** NuGet package to the newly created application by using the `NuGet Package Manager`. Right-click the project and select Manage NuGet Packages.

    ![nuget explorer](images/mac-wasm-nuget-explorer.png)

2. Search **Syncfusion.Blazor** keyword in the Browse tab and install **Syncfusion.Blazor** NuGet package in the application.

    ![select nuget](images/mac-wasm-sync-pack.png)

3. The Syncfusion Blazor package will be installed in the project, once the installation process is completed.

4. Open **~/_Imports.razor** file and import the `Syncfusion.Blazor`.

    ```csharp
    @using Syncfusion.Blazor
    @using Syncfusion.Blazor.Calendars
    ```

5. Open the **~/Program.cs** file and register the Syncfusion Blazor Service.

    ```csharp
    using Syncfusion.Blazor;

    namespace WebApplication1
    {
        public class Program
        {
            public static async Task Main(string[] args)
            {
                ....
                ....
                builder.Services.AddSyncfusionBlazor();
                await builder.Build().RunAsync();
            }
        }
    }
    ```

6. Add the Syncfusion bootstrap4 theme in the `<head>` element of the **~/wwwroot/index.html** page.

    ```html
    <head>
        ....
        ....
        <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    </head>
    ```
    > **Note:** The same theme file can be referred through the CDN version by using [https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css](https://cdn.syncfusion.com/blazor/18.2.57/styles/bootstrap4.css).
    >
    > To use manual scripts other than the scripts from NuGet package, register the Blazor service in **~/Program.cs** file by using true parameter as mentioned below.
    >
    > ```csharp
    > using Syncfusion.Blazor;
    >
    > namespace WebApplication1
    > {
    >     public class Program
    >   {
    >         public static async Task Main(string[] args)
    >         {
    >            ....
    >            ....
    >            builder.Services.AddSyncfusionBlazor(true);
    >            await builder.Build().RunAsync();
    >         }
    >     }
    > }
    >
    > ```

7. Now, add the Syncfusion Blazor components in any web page (razor) in the `Pages` folder. For example, the calendar component is added in the **~/Pages/Index.razor** page.

    ```csharp
    <SfCalendar TValue="DateTime"></SfCalendar>
    ```

8. Run the application. The Syncfusion Blazor Calendar component will render in the web browser.

    ![output](images/browser-output.png)
