<!-- markdownlint-disable MD024 -->

# Getting started with Syncfusion Blazor - Server App in .NET Core CLI

This article provides a step-by-step introduction to configure Syncfusion Blazor setup, build and run a simple Blazor Server application using the [.NET Core CLI](https://dotnet.microsoft.com/download/dotnet-core/3.1).

> **Note:** Starting with version 17.4.0.39 (2019 Volume 4), you need to include a valid license key (either paid or trial key) within your applications. Please refer to this [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#blazor) for more information.

## Prerequisites

* [.NET Core SDK 3.1.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## Create a Blazor Server project using .NET Core CLI

1. Run the following command line to create a new Blazor Server application.
  
    ```bash
        dotnet new blazorserver -o WebApplication1
        cd WebApplication1
    ```

   Importing Syncfusion Blazor component in the application

2. Now, add **Syncfusion.EJ2.Blazor** NuGet package to the new application using below command line.

    ```bash
        dotnet add package Syncfusion.EJ2.Blazor -v '{:nuget-version:}'
        dotnet restore
    ```

3. The Syncfusion Blazor package will be included in the newly created project after the installation process is completed.

4. Open **~/_Imports.razor** file and import the `Syncfusion.EJ2.Blazor`.

   ```csharp
    @using Syncfusion.EJ2.Blazor
    @using Syncfusion.EJ2.Blazor.Calendars
    ```

5. Open the **~/Startup.cs** file and register the Syncfusion Blazor Service.

    ```csharp
    using Syncfusion.EJ2.Blazor;

    namespace WebApplication1
    {
        public class Startup
        {
            public void ConfigureServices(IServiceCollection services)
            {
                ....
                ....
                services.AddSyncfusionBlazor();
            }
        }
    }
    ```

6. Add the client-side resources through CDN in the `<head>` element of the **~/Pages/_Host.cshtml** page.

    ```html
    <head>
        ....
        ....
        <link href="https://cdn.syncfusion.com/ej2/{:version:}/material.css" rel="stylesheet" />
        <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ej2.min.js"></script>
        <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ejs.interop.min.js"></script>
    </head>
    ```

    > **Note:** For production purpose and minimal requirement, Syncfusion provides an option to generate scripts and styles of selective control by using the Custom Resource Generator ([CRG](https://crg.syncfusion.com/)) web tool. Refer to this help documentation [link](../common/custom-resource-generator) for more details on CRG.

7. Now, add the Syncfusion Blazor components in any web page (razor) in the `~/Pages` folder. For example, the calendar component is added in the **~/Pages/Index.razor** page.

    ```csharp
    <EjsCalendar TValue="DateTime"></EjsCalendar>
    ```

8. Run `dotnet run` command to run the application. The Syncfusion Blazor Calendar component will render in the web browser.

    ![output](images/browser-output.png)
