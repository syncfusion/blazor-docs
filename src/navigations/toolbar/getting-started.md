---
title: "Getting Started"
component: "Toolbar"
description: "Rendering Toolbar using Blazor."
---

# Getting Started

This section briefly explains about how to include a `Toolbar` in your Blazor server-side application. You can refer [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](../getting-started/server-side-blazor/) page for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in the application

1. Install **Syncfusion.Blazor** NuGet package to the application by using the `NuGet Package Manager`.

2. You can add the client-side resources through CDN or from NuGet package in the `<head>` element of the **~/Pages/_Host.cshtml** page.

 ```html
    <head>
        ...
            <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
            @*<link href="https://cdn.syncfusion.com/blazor/{{version}}/styles/{{theme}}.css " rel="stylesheet" />*@
        ...
    </head>
```

> For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](../../common/how-to/render-blazor-server-app-in-ie/) for more information.

 ```html
    <head>
        ...
            <link href="https://cdn.syncfusion.com/blazor/{{version}}/styles/{{theme}}.css" rel="stylesheet" />
            <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
        ...
    </head>
```

## Adding component package to the application

Open `~/_Imports.razor` file and import the `Syncfusion.Blazor.Navigations` package.

```csharp
    @using Syncfusion.Blazor.Navigations
```

## Add SyncfusionBlazor service in Startup file

Open the **Startup.cs** file and add services required by Syncfusion components using  **services.AddSyncfusionBlazor()** method. Add this method in the **ConfigureServices** function as follows.

```csharp
using Syncfusion.Blazor;

namespace BlazorApplication
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
    }
}
```

> To enable custom client side resource loading from CRG or CDN. You need to disable resource loading by `AddSyncfusionBlazor(true)` and load the scripts in the HEAD element of the `~/Pages/_Host.cshtml` page.

 ```html
    <head>
        ...
            <link href="https://cdn.syncfusion.com/blazor/{{version}}/styles/{{theme}}.css" rel="stylesheet" />
            <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js"></script>
        ...
    </head>
```

## Adding Toolbar component to the application

Now, add the Syncfusion Blazor Toolbar component in any web page (razor) in the `Pages` folder. For example, the Toolbar component is added in the `~/Pages/Index.razor` page.

```csharp
@using Syncfusion.Blazor.Navigations

<SfToolbar>
    <ToolbarItems>
        <ToolbarItem Text="Cut"></ToolbarItem>
        <ToolbarItem Text="Copy"></ToolbarItem>
        <ToolbarItem Text="Paste"></ToolbarItem>
        //To separate the Toolbar items
        <ToolbarItem></ToolbarItem>
        <ToolbarItem Text="Bold"></ToolbarItem>
        <ToolbarItem Text="Unde rline"></ToolbarItem>
        <ToolbarItem Text="Italic"></ToolbarItem>
        <ToolbarItem Text="Color-Picker"></ToolbarItem>
    </ToolbarItems>
</SfToolbar>
```

To get start quickly with Blazor Toolbar, you can also check on this video:

`youtube:3brT3ztZErE`

## Run the application

After successful compilation of your application, simply press `F5` to run the application.

![Dfeault Toolbar](./images/browser-output.png)

## See Also

1. [Getting Started with Syncfusion Blazor for client-side in .NET Core CLI](../getting-started/blazor-webassembly-dotnet-cli/)
2. [Getting Started with Syncfusion Blazor for client-side in Visual Studio 2019](../getting-started/blazor-webassembly/)
3. [Getting Started with Syncfusion Blazor for server-side in .NET Core CLI](../getting-started/server-side-blazor-dotnet-cli/)