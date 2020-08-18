---
title: "ListView Getting Started"
component: "ListView"
description: "Learn how to create ListView control in Blazor application."
---

<!-- markdownlint-disable MD024 -->

# Getting Started

This section briefly explains about how to include a `ListView` in your Blazor server-side application. You can refer
[Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/server-side-blazor/) page for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in the application

* Install **Syncfusion.Blazor** NuGet package to the application by using the `NuGet Package Manager`.
>Note:Please ensure to check the Include **prerelease** option for our Beta release.

* You can add the client-side style resources using NuGet package to the `<head>` element of the `~/wwwroot/index.html` page in Blazor WebAssembly app or `~/Pages/_Host.cshtml` page in Blazor Server app.
>Note: You can also add the client-side style resources through CDN.

```html
<head>
    ....
    ....
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
</head>
```

```html
<head>
    <link href="https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css" rel="stylesheet" />
</head>

```

* For `Internet Explorer 11` kindly refer the polyfills. Refer the [documentation](https://blazor.syncfusion.com/documentation/common/how-to/render-blazor-server-app-in-ie/) for more information.

```html
<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
</head>
```

## Add Syncfusion Blazor service in Startup.cs (Server-side application)

Open the **Startup.cs** file and add services required by Syncfusion components using `services.AddSyncfusionBlazor()` method. Add this method in the **ConfigureServices** function as follows.

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

## Add Syncfusion Blazor service in Program.cs (Client-side application)

Open the **Program.cs** file and add services required by Syncfusion components using `builder.services.AddSyncfusionBlazor()` method. Add this method in the **Main** function as follows.

```csharp

using Syncfusion.Blazor;

namespace BlazorApplication
{
    public class Program
    {
        ....
        ....
        public static async Task Main(string[] args)
        {
            ....
            ....
            builder.Services.AddSyncfusionBlazor();
        }
    }
}

```

>Note: To enable custom client side resource loading from CRG or CDN. You need to disable resource loading by **AddSyncfusionBlazor(true)** and load the scripts to the `<head>` element of the **~/wwwroot/index.html** page in Blazor WebAssembly app or **~/Pages/_Host.cshtml** page in Blazor Server app. You can generate scripts for required components alone using CRG. Refer [here](https://blazor.syncfusion.com/documentation/common/custom-resource-generator/) for more details on CRG.

```csharp
<head>
    <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js"></script>
</head>
```

## Adding ListView component namespace to the application

Open `~/_Imports.razor` file and import the `Syncfusion.Blazor.Lists` package.

```csharp
    @using Syncfusion.Blazor.Lists
```

## Adding ListView component to the application

Add the Syncfusion Blazor ListView component in any web page (razor) in the `Pages` folder. For example, the ListView component is added in the **~/Pages/Index.razor** page.

```csharp

@using Syncfusion.Blazor.Lists

<SfListView DataSource="@Data">
    <ListViewFieldSettings Id="Id" Text="Text"></ListViewFieldSettings>
</SfListView>

@code
{
    private DataModel[] Data =
     {
            new DataModel { Text = "ArtWork", Id = "list-01" },
            new DataModel { Text = "Abstract", Id = "list-02" },
            new DataModel { Text = "Modern Painting", Id = "list-03" },
            new DataModel { Text = "Ceramics", Id = "list-04" },
            new DataModel { Text = "Animation Art", Id = "list-05" },
            new DataModel { Text = "Oil Painting", Id = "list-06" }
    };
    class DataModel
    {
        public string Text { get; set; }
        public string Id { get; set; }
    }
}

```

## Run the application

After successful compilation of your application, simply press `F5` to run the application.

Output be like the below.

![ListView Sample](./images/listview.png)

## See Also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/blazor-webassembly-dotnet-cli/)

* [Getting Started with Syncfusion Blazor for Client-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/blazor-webassembly/)

* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/server-side-blazor-dotnet-cli/)