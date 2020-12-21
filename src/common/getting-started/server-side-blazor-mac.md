<!-- markdownlint-disable MD024 -->

# Getting started with Syncfusion Blazor - Server App in Visual Studio for Mac

This article provides a step-by-step introduction to configure Syncfusion Blazor setup, build and run a simple Blazor Server application using [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/).

> **Note:** Starting with version 17.4.0.39 (2019 Volume 4), you need to include a valid license key (either paid or trial key) within your applications. Please refer to this [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#blazor) for more information.

## Prerequisites

* [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)
* [.NET Core SDK 3.1.8](https://dotnet.microsoft.com/download/dotnet-core/3.1) / [.NET 5.0 SDK](https://dotnet.microsoft.com/download/dotnet/5.0)

>**.NET Core SDK 3.1.8** requires Visual Studio for Mac 8.7.6 or later.
>
> **.NET 5.0** requires Visual Studio 2019 for Mac 8.8 or later.

## Create a Blazor Server project in Visual Studio for Mac

1. Choose **New** from the Visual Studio for Mac dashboard.

    ![new project in blazor](images/mac-new-project.png)

2. Select **Blazor Server App** from the template and click the **Next** button.

    ![blazor template](images/mac-server-template.png)

3. Continue with **No Authentication** selection in Authentication and click **Next** button.

    ![blazor authentication](images/mac-server-authentication.png)

4. Now, the Blazor Server App project configuration window will popup. Click **Create** button to create a new project after filling Project name.

    ![blazor project configuration](images/mac-server-project-config.png)

## Importing Syncfusion Blazor component in the application

* Starting with Volume 4, 2020 (v18.4.0.30) release, Syncfusion provides [individual NuGet packages](https://blazor.syncfusion.com/documentation/nuget-packages/) for our Syncfusion Blazor components.

    > **Note:** You can use anyone of the below standards to add Syncfusion components in your Blazor application.

### Using Syncfusion individual NuGet Package [Suggested - New standard from v18.4.0.30]

1. Now, install **Syncfusion.Blazor.Calendars** NuGet package to the new application using the below command line. For more details about available NuGet packages, refer to the [Individual NuGet Packages](https://blazor.syncfusion.com/documentation/nuget-packages/) documentation.

    ![nuget explorer](images/mac-server-nuget-explorer.png)

2. Search **Syncfusion.Blazor.Calendars** keyword in the Browse tab and install **Syncfusion.Blazor.Calendars** NuGet package in the application.

3. The Syncfusion Blazor Calendars package will be installed in the project, Once the installation process is completed.

4. Open **~/_Imports.razor** file and import the `Syncfusion.Blazor` namespace.

    ```csharp
    @using Syncfusion.Blazor
    @using Syncfusion.Blazor.Calendars
    ```

5. Open the **~/Startup.cs** file and register the Syncfusion Blazor Service.

    ```csharp
    using Syncfusion.Blazor;

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

6. Add the Syncfusion bootstrap4 theme in the `<head>` element of the **~/Pages/_Host.cshtml** page.

    ```html
    <head>
        ....
        ....
        <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
    </head>
    ```

    > Warning: `Syncfusion.Blazor` package should not install along with [individual NuGet packages](https://blazor.syncfusion.com/documentation/nuget-packages/). Hence, you have to use `Syncfusion.Blazor.Themes` package for applying Syncfusion themes in the application.

### Using Syncfusion.Blazor NuGet Package [Previous standard before v18.4.0.30]

> Warning: If you have used the above individual NuGet package standard, then skip this section. If you use both standards in the same project, it will throw ambiguous errors while compiling the application.

1. Now, install **Syncfusion.Blazor** NuGet package to the newly created application by using the `NuGet Package Manager`. Right-click the project and select Manage NuGet Packages.

    ![nuget explorer](images/mac-server-nuget-explorer.png)

2. Search **Syncfusion.Blazor** keyword in the Browse tab and install **Syncfusion.Blazor** NuGet package in the application.

    ![select nuget](images/mac-server-sync-pack.png)

3. The Syncfusion Blazor package will be installed in the project, Once the installation process is completed.

4. Open **~/_Imports.razor** file and import the `Syncfusion.Blazor`.

    ```csharp
    @using Syncfusion.Blazor
    @using Syncfusion.Blazor.Calendars
    ```

5. Open the **~/Startup.cs** file and register the Syncfusion Blazor Service.

    ```csharp
    using Syncfusion.Blazor;

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

6. Add the Syncfusion bootstrap4 theme in the `<head>` element of the **~/Pages/_Host.html** page.

    ```html
    <head>
        ....
        ....
        <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
    </head>
    ```

    > **Note:** The same theme file can be referred through the CDN version by using [https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css](https://cdn.syncfusion.com/blazor/18.3.47/styles/bootstrap4.css).

## Adding Syncfusion Component and Run the Application

1. Now, add the Syncfusion Blazor components in any web page (razor) in the `~/Pages` folder. For example, the Calendar component is added in the **~/Pages/Index.razor** page.

    ```csharp
    <SfCalendar TValue="DateTime"></SfCalendar>
    ```

2. Run the application, The Syncfusion Blazor Calendar component will render in the default web browser.

    ![output](images/mac-output.png)
