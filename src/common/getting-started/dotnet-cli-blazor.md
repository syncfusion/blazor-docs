<!-- markdownlint-disable MD024 -->

# Getting started with Syncfusion Blazor - WebAssembly App in .NET Core CLI

This article provides a step-by-step introduction to configure Syncfusion Blazor for Blazor setup, build and run a simple Blazor WebAssembly application using [.NET Core CLI](https://dotnet.microsoft.com/download/dotnet-core/3.1).

> **Note:** Starting with version 17.4.0.39 (2019 Volume 4), you need to include a valid license key (either paid or trial key) within your applications. Please refer to this [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#blazor) for more information.
> Blazor is an unsupported, experimental web framework that shouldn't be used for production workloads at this time.

## Prerequisites

* [.NET Core SDK 3.1.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## Create a Blazor WebAssembly project using .NET Core CLI

1. Install the Blazor project templates by using below command line in the command prompt:

```bash
    dotnet new -i Microsoft.AspNetCore.Blazor.Templates::3.2.0-preview1.20073.1
    ````

2. Once project templates installed, run the following command line to create a new Blazor WebAssembly application.

## Importing Syncfusion Blazor component in the application

1. Now, add **Syncfusion.EJ2.Blazor** NuGet package to the new application using below command line.

    ```bash
        dotnet add package Syncfusion.EJ2.Blazor -v '{:nuget-version:}'
        dotnet restore
    ```

2. The Syncfusion Blazor package will be included in the newly created project after the installation process is completed.

3. Open **~/_Imports.razor** file and import the `Syncfusion.EJ2.Blazor`.

    ```csharp
    @using Syncfusion.EJ2.Blazor
    @using Syncfusion.EJ2.Blazor.Calendars
    ```

4. Open the **~/Program.cs** file and register the Syncfusion Blazor Service.

    ```csharp
    using Syncfusion.EJ2.Blazor;

    namespace WebApplication1
    {
        public class Program
        {
            public static async Task Main(string[] args)
            {
                ....
                ....
                builder.Services.AddSyncfusionBlazor();
                await.builder.Build.RunAsync();
            }
        }
    }
    ```

5. Add the client-side resource through CDN in the `<head>` element of the **~/wwwroot/index.html** page.

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

6. Now, add the Syncfusion Blazor components in any web page (razor) in the `~/Pages` folder. For example, the calendar component is added in the **~/Pages/Index.razor** page.

    ```csharp
    <EjsCalendar TValue="DateTime"></EjsCalendar>
    ```

7. Run `dotnet run` command to run the application. The Syncfusion Blazor Calendar component will render in the web browser.

    ![output](images/browser-output.png)
