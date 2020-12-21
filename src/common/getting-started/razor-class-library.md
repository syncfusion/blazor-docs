# Creating Razor Class Library (RCL) using Syncfusion Blazor components

This section provides information about creating Razor Class Library with the Syncfusion Blazor components using [Visual Studio 2019](https://visualstudio.microsoft.com/vs/).

## Prerequisites

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [.NET Core SDK 3.1.8](https://dotnet.microsoft.com/download/dotnet-core/3.1) / [.NET 5.0 SDK](https://dotnet.microsoft.com/download/dotnet/5.0)

> **.NET Core SDK 3.1.8** requires Visual Studio 2019 16.7 or later.
>
> **.NET 5.0** requires Visual Studio 2019 16.8 or later.

## Create a Razor Class Library using Syncfusion Blazor components in Visual Studio 2019

1. Choose **Create a new project** from the Visual Studio dashboard.

    ![new project in aspnetcore blazor](images/new-project.png)

2. Select **Razor Class Library** from the template and click the **Next** button.

    ![razor class template](images/razor-project-configuration.png)

3. Now, the project configuration window will popup. Click **Create** button to create a new project with the default project configuration.

    ![razor class project configuration](images/razor-class-template.png)

4. Choose **Razor Class Library** from the dashboard and click **Create** button to create a new Razor Class Library Server application. Select the target framework **.NET Core 3.1**  or **.NET5.0** at the top based on your required target that you want.

    ![select framework](images/razor-class-server-template.png)

    > **Note:** If exist netstandard version is 2.0 in `RazorClassLibrary.csproj`, change it to **netstandard2.1**
    >
    > ```csharp
    > <PropertyGroup>
    >   <TargetFramework>netstandard2.1</TargetFramework>
    >   ....
    > </PropertyGroup>
    > ```

## Importing Syncfusion Blazor component in Razor Class Library

* Starting with Volume 4, 2020 (v18.4.0.30) release, Syncfusion provides [individual NuGet packages](https://blazor.syncfusion.com/documentation/nuget-packages/) for our Syncfusion Blazor components.

    > **Note:** You can use anyone of the below standards to add Syncfusion components in your Blazor application.

### Using Syncfusion individual NuGet Package [Suggested - New standard from v18.4.0.30]

1. Now, install **Syncfusion.Blazor.Calendars** NuGet package to the newly created RLC by using the `NuGet Package Manager`. For more details about available NuGet packages, refer to the [Individual NuGet Packages](https://blazor.syncfusion.com/documentation/nuget-packages/) documentation.

2. Right-click the project and select Manage NuGet Packages. 

    ![nuget explorer](images/rcl-nuget-explorer.png)

3. Search **Syncfusion.Blazor.Calendars** keyword in the Browse tab and install **Syncfusion.Blazor.Calendars** NuGet package in RLC.

    ![select nuget](images/individual-nuget.png)

3. The Syncfusion Blazor Calendars package will be installed in the project, Once the installation process is completed.

4. Open **~/_Imports.razor** file in RLC and import the `Syncfusion.Blazor.Calendars`.

    ```csharp
    @using Syncfusion.Blazor.Calendars
    ```

 5. Add the Syncfusion bootstrap4 theme in the `<head>` element of the **~/Pages/_Host.html** page in Blazor App.

    ```html
    <head>
        ....
        ....

        <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
    </head>
    ```

    > Warning: `Syncfusion.Blazor` package should not install along with [individual NuGet packages](https://blazor.syncfusion.com/documentation/nuget-packages/). Hence, you have to use `Syncfusion.Blazor.Themes` package for applying Syncfusion themes in the application.

6. Now, import and add the Syncfusion Blazor components in the `~/Component.razor` file. For example, the Calendar component is imported and added in the **~/Component.razor** page.

    ```csharp

    <div class="my-component">
    This Blazor component is defined in the <strong>RazorClassLibrary</strong> package.
    </div><br />

    <SfCalendar TValue="DateTime"></SfCalendar>
    ```

### Using Syncfusion.Blazor NuGet Package [Previous standard before v18.4.0.30]

> Warning: If you have used the above individual NuGet package standard, then skip this section. If you use both standards in the same project, it will throw ambiguous errors while compiling the application.

1. Now, install **Syncfusion.Blazor** NuGet package to the newly created RLC by using the `NuGet Package Manager`. Right-click the project and select Manage NuGet Packages.

    ![nuget explorer](images/rcl-nuget-explorer.png)

2. Search **Syncfusion.Blazor** keyword in the Browse tab and install **Syncfusion.Blazor** NuGet package in RLC.

    ![select nuget](images/select-nuget.png)

3. The Syncfusion Blazor package will be installed in the project, Once the installation process is completed.

4. Open **~/_Imports.razor** file in RLC and import the `Syncfusion.Blazor`.

    ```csharp
    @using Syncfusion.Blazor
    ```

 5. Add the Syncfusion bootstrap4 theme in the `<head>` element of the **~/Pages/_Host.html** page in Blazor App.

    ```html
    <head>
        ....
        ....

          <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    </head>
    ```

    > **Note:** The same theme file can be referred through the CDN version by using [https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css](https://cdn.syncfusion.com/blazor/18.4.30/styles/bootstrap4.css).

6. Now, import and add the Syncfusion Blazor components in the `~/Component.razor` file. For example, the Calendar component is imported and added in the **~/Component.razor** page.

    ```csharp
    @using Syncfusion.Blazor.Calendars

    <div class="my-component">
    This Blazor component is defined in the <strong>RazorClassLibrary</strong> package.
    </div><br />

    <SfCalendar TValue="DateTime"></SfCalendar>
    ```

## Create a Blazor Server project in Visual Studio 2019 with Razor Class Library (RCL)

1. Choose **Create a new project** from the Visual Studio dashboard.

    ![new project in aspnetcore blazor](images/new-project.png)

2. Select **Blazor App** from the template and click the **Next** button.

    ![blazor template](images/blazor-template.png)

3. Now, the project configuration window will popup. Click **Create** button to create a new project with the default project configuration.

    ![asp.net core project configuration](images/blazorapp-template.png)

4.  Select the target Framework **ASP.NET Core 3.1** or **.NET 5.0** at the top of the Application based on your required target information.

    ![select framework](images/blazor-select-template.png)

5. Choose **Blazor Server App** from the dashboard and click **Create** button to create a new Blazor Server application. 

    ![select framework](images/blazor-server-template.png)

    > **Note:** ASP.NET Core 3.1 available in Visual Studio 2019 version.

## Configure the Razor Class Library and Blazor Server Application

1. Now, Right-click the solution and select Add/Existing Project.

    ![razor class library in blazor app](images/blazor-configure.png)

2. Add the **Razor Class Library** project by selecting `RazorClassLibrary.csproj` file.

    ![add RCL in blazor app](images/blazor-razor-configure.png)

    > **Note:** Razor Class Library project is added to existing Blazor Server Application.

3. Right-click the Blazor App project and select Add/Project reference. Now click the checkbox and configure the **Razor Class Library** and **Blazor Server Application**.

    ![reference manager in blazor app](images/reference-manager.png)

    ![select RCL to configure blazor app](images/configure-razor.png)

## Importing Razor Class Library in the Blazor Server Application

1. Open **~/_Imports.razor** file in Blazor App and import the `RazorClassLibrary`.

    ```csharp
    @using RazorClassLibrary
    ```

2. Open the **~/Startup.cs** file and register the Syncfusion Blazor Service from RCL.

    ```csharp
    ....
    using Syncfusion.Blazor;
    namespace BlazorApp
    {
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
        }
    }
    ```

3. Add the Syncfusion bootstrap4 theme in the `<head>` element of the **~/Pages/_Host.html** page in Blazor App.

    ```html
    <head>
        ....
        ....

        <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
    </head>
    ```

    > **Note:** The same theme file can be referred through the CDN version by using [https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css](https://cdn.syncfusion.com/blazor/18.4.30/styles/bootstrap4.css).
   

4. Now, add the created custom component that imported with Syncfusion Blazor component from Razor Class Library in any web page (razor) in the `~/Pages` folder. For example, the custom component with imported Syncfusion Blazor Calendar component from Razor Class Library is added to the **~/Pages/Index.razor** page as like below.

    ```csharp
    <Component></Component>
    ```

5. Run the application, The Syncfusion Blazor Calendar component will render in the default web browser.

    ![RCL output](images/rcl-output.png)

## Create a Blazor WebAssembly project in Visual Studio 2019 with Razor Class Library (RCL)

1. Choose **Create a new project** from the Visual Studio dashboard.

    ![new project in aspnetcore blazor](images/new-project.png)

2. Select **Blazor App** from the template and click the **Next** button.

    ![blazor template](images/blazor-template.png)

3. Now, the project configuration window will popup. Click **Create** button to create a new project with the default project configuration.

    ![asp.net core project configuration](images/blazorapp-template.png)

4.Select the target Framework **ASP.NET Core 3.1** or **.NET 5.0** at the top of the Application based on your required target information.

    ![select framework](images/blazor-select-template.png)

5. Choose **Blazor WebAssembly App** from the dashboard and click **Create** button to create a new Blazor WebAssembly application. 

    ![select framework](images/webassembly-template.png)

    > **Note:** ASP.NET Core 3.1 available in Visual Studio 2019 version.

## Configure the Razor Class Library and Blazor WebAssembly Application

1. Now, Right-click the solution and select Add/Existing Project.

    ![razor class library in blazor app](images/blazor-configure.png)

2. Add the **Razor Class Library** project by selecting `RazorClassLibrary.csproj` file.

    ![add RCL in blazor app](images/blazor-razor-configure.png)

    > **Note:** Razor Class Library project is added to existing Blazor WebAssembly Application.

3. Right-click the Blazor App project and select Add/Project reference. Now click the checkbox and configure the **Razor Class Library** and **Blazor WebAssembly Application**.

    ![reference manager in blazor app](images/reference-manager.png)

    ![select RCL to configure blazor app](images/configure-razor.png)

## Importing Razor Class Library in the Blazor WebAssembly Application

1. Open **~/_Imports.razor** file in Blazor WebAssembly App and import the `RazorClassLibrary`.

    ```csharp
    @using RazorClassLibrary
    ```

2. Open the **~/Program.cs** file and register the Syncfusion Blazor Service from RCL.

    ```csharp
    using Syncfusion.Blazor;

    namespace BlazorApp
    {
        public class Program
        {
            public static async Task Main(string[] args)
            {
                ....
                ....
                builder.Services.AddSyncfusionBlazor();
                await builder.Build.RunAsync();
            }
        }
    }
    ```

   

4. Now, add the created custom component that imported with Syncfusion Blazor component from Razor Class Library in any web page (razor) in the `~/Pages` folder. For example, the custom component with imported Syncfusion Blazor Calendar component from Razor Class Library is added to the **~/Pages/Index.razor** page as like below.

    ```csharp
    <Component></Component>
    ```

5. Run the application, The Syncfusion Blazor Calendar component will render in the default web browser.

    ![RCL output](images/rcl-output.png)
