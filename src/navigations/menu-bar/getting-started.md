---
component: "Menu Bar"
---

# Getting Started with Blazor Menu Bar Component

This section briefly explains about how to include Menu Bar Component in your Blazor server-side  application. You can refer [Getting Started with Syncfusion Blazor for Server-side in Visual Studio 2019 page](https://blazor.syncfusion.com/documentation/getting-started/blazor-server-side-visual-studio-2019/) page for the introduction and configuring the common specifications.

To get start quickly with Menu Bar Component using Blazor, you can check on this video:

`youtube:TBoUetqLnps`

## Importing Syncfusion Blazor component in the application

1. Install the **Syncfusion.Blazor** NuGet package to the application by using the `NuGet Package Manager`.

2. You can add the client-side style resources through CDN or from NuGet package in the `<head>` element of the `~/Pages/_Host.chtml` page.

> Please ensure to check the **Include prerelease** option.

```csharp
<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    @*<link href="https://cdn.syncfusion.com/blazor/{:version:}/bootstrap4.css" rel="stylesheet" />*@
</head>
```

For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](https://blazor.syncfusion.com/documentation/common/how-to/render-blazor-server-app-in-ie/) for more information.

```csharp
<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
</head>
```

## Adding component package to the application

Open `/_Imports.razor file` and import the **Syncfusion.Blazor.Navigations** package.

```csharp

@using Syncfusion.Blazor.Navigations

```

## Add SyncfusionBlazor service in Startup.cs

Open the **Startup.cs** file and add services required by Syncfusion components.
Add **services.AddSyncfusionBlazor()** method in the ConfigureServices function as follows.

```csharp
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

> To enable custom client side resource loading from CRG or CDN. You need to disable resource loading by **AddSyncfusionBlazor(true)** and load the scripts in the HEAD element of the **~/Pages/_Host.cshtml** page.

```csharp
<head>
    <environment include="Development">
        <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js">
        </script>
    </environment>
</head>
```

## Adding Menu Bar component to the application

Now, add the Blazor Menu Bar component in `razor` page in the `Pages` folder. For example, the Menu Bar component is added in the `~/Pages/Index.razor` page.

```csharp
@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems"></SfMenu>

@code {
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem{ Text = "File", Items = new List<MenuItem>{
            new MenuItem{ Text= "Open" },
            new MenuItem{ Text= "Save" },
            new MenuItem{ Text= "Exit" }}
    },
        new MenuItem{ Text = "Edit", Items = new List<MenuItem>{
            new MenuItem{ Text= "Cut" },
            new MenuItem{ Text= "Copy" },
            new MenuItem{ Text= "Paste" }}
    },
        new MenuItem{ Text = "View", Items = new List<MenuItem>{
            new MenuItem{ Text = "Toolbars" },
            new MenuItem{ Text = "Zoom" },
            new MenuItem{ Text = "Full Screen" }}
    },
        new MenuItem{ Text = "Tools", Items = new List<MenuItem>{
            new MenuItem{ Text= "Spelling & Grammar" },
            new MenuItem{ Text= "Customize" },
            new MenuItem{ Text= "Options" }}
    },
        new MenuItem{ Text = "Go" },
        new MenuItem{ Text = "Help" }
    };
}

```

## Run the application

After successful compilation of your application, simply press F5 to run the application. The Blazor Menu Bar component will render in the web browser as shown below

![Menu Sample](./images/menu.png)

## See Also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/blazor-webassembly-dotnet-cli/)
* [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/blazor-server-side-visual-studio-2019/)
* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/blazor-server-side-dotnet-cli/)