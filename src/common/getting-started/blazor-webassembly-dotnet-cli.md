<!-- markdownlint-disable MD024 -->

# Getting started with Syncfusion Blazor - WebAssembly App in .NET Core CLI

This article provides a step-by-step introduction to configure Syncfusion Blazor setup, build and run a simple Blazor WebAssembly application using [.NET Core CLI](https://dotnet.microsoft.com/download/dotnet-core/3.1).

> **Note:** Starting with version 17.4.0.39 (2019 Volume 4), you need to include a valid license key (either paid or trial key) within your applications. Please refer to this [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#blazor) for more information.

## Prerequisites

* [.NET Core SDK 3.1.8](https://dotnet.microsoft.com/download/dotnet-core/3.1) / [.NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)

## Create a Blazor WebAssembly project using .NET Core CLI

1. Run the following command line to create a new Blazor WebAssembly application.

    ```bash
        dotnet new blazorwasm -o WebApplication1
        cd WebApplication1
    ```

## Importing Syncfusion Blazor component in the application

### Using Syncfusion individual Nuget Package

1. Now, add **Syncfusion.Blazor.Calendars** NuGet package to the new application using the below command line. For more details about available NuGet packages, refer to the [Individual NuGet Packages](../nuget-packages/) documentation.

    ```bash
        dotnet add package Syncfusion.Blazor.Calendars -v '{:nuget-version:}'
        dotnet restore
    ```

2. The Syncfusion Blazor package will be included in the newly created project after the installation process is completed.

3. Open **~/_Imports.razor** file and import the `Syncfusion.Blazor`.

    ```csharp
    @using Syncfusion.Blazor
    @using Syncfusion.Blazor.Calendars
    ```

4. Open the **~/Program.cs** file and register the Syncfusion Blazor Service.

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

5. Add the Syncfusion bootstrap4 theme in the `<head>` element of the **~/wwwroot/index.html** page.

    ```html
    <head>
        ....
        ....
        <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
    </head>
    ```

### Using Syncfusion Blazor Nuget Package

1. Now, add **Syncfusion.Blazor** NuGet package to the new application using the below command line.

    ```bash
        dotnet add package Syncfusion.Blazor -v '{:nuget-version:}'
        dotnet restore
    ```

2. The Syncfusion Blazor package will be included in the newly created project after the installation process is completed.

3. Open **~/_Imports.razor** file and import the `Syncfusion.Blazor`.

    ```csharp
    @using Syncfusion.Blazor
    @using Syncfusion.Blazor.Calendars
    ```

4. Open the **~/Program.cs** file and register the Syncfusion Blazor Service.

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

5. Add the Syncfusion bootstrap4 theme in the `<head>` element of the **~/wwwroot/index.html** page.

    ```html
    <head>
        ....
        ....
         <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    </head>
    ```

    > **Note:** The same theme file can be referred through the CDN version by using [https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css](https://cdn.syncfusion.com/blazor/18.4.30/styles/bootstrap4.css).
   

## Adding Syncfusion Component And Run the Application

1. Now, add the Syncfusion Blazor components in any web page (razor) in the `~/Pages` folder. For example, the calendar component is added in the **~/Pages/Index.razor** page.

    ```csharp
    <SfCalendar TValue="DateTime"></SfCalendar>
    ```

2. Run `dotnet run` command to run the application. The Syncfusion Blazor Calendar component will render in the web browser.

    ![output](images/browser-output.png)
