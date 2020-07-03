---
title: "Getting Started with ASP.NET Core Blazor server-side in Visual Studio 2019"
component: "Progress Bar"
description: "This section briefly explains how to create the Progress Bar component and configure its available functionalities in Blazor server-side web application and also how to include a simple Progress Bar in your Blazor server-side web application"
---

<!-- markdownlint-disable MD040 -->

# Getting Started in Blazor Progress Bar

This section briefly explains about how to include a `Progress Bar` in your Blazor server-side application. You can refer [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/blazor-webassembly/) page for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in the application

1. Install Syncfusion.Blazor NuGet package to the application by using the NuGet Package Manager. Please ensure to check the **Include prerelease** option.
2. You can add the client-side style resources through CDN or from NuGet package in the `HEAD` element of the `~/Pages/_Host.cshtml` page.

```html
<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
</head>
```

**Note:** The same theme file can be referred through the CDN version by using `https://cdn.syncfusion.com/blazor/18.1.36-beta/styles/bootstrap4.css`

> For Internet Explorer 11 kindly refer the polyfills. Refer the [`documentation`](https://blazor.syncfusion.com/documentation/common/how-to/render-blazor-server-app-in-ie/) for more information.

```html
<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
</head>
```

## Adding component package to the application

Open `**~/_Imports.razor` file and import the `Syncfusion.Blazor.**`

```csharp
@using Syncfusion.Blazor
@using Syncfusion.Blazor.ProgressBar
```

## Add SyncfusionBlazor service in Startup.cs

Open the **Startup.cs** file and add services required by Syncfusion components using **service.AddSyncfusionBlazor()** method. Add this method in the **ConfigureServices** function as follows.

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

**Note:** To enable custom client side resource loading from CRG or CDN. You need to disable resource loading by `AddSyncfusionBlazor(true)` and load the scripts in the **HEAD** element of the **~/Pages/_Host.cshtml** page.

```csharp
<head>
    <script src="https://cdn.syncfusion.com/blazor/18.1.36-beta/dist/syncfusion-blazor.min.js"></script>
</head>
```

## Adding Progress Bar component to the application

Now, add the Syncfusion Blazor components in any web page (razor) in the Pages folder. For example, the Progress Bar component is added in the **~/Pages/Index.razor** page.

```csharp
<SfProgressBar Value="50" Minimum="0" Maximum="100" TrackThickness="12" ProgressThickness="12">
</SfProgressBar>
```

## Run the application

After successful compilation of your application, the Syncfusion Blazor Progress Bar component will render in the web browser.

![progress bar](images/linear.png)

## Progress Type

You can change the type of progress bar by using `Type` property. By default `Linear` type of progress bar will render. In the below example you can see the `Circular` type.

```csharp
<SfProgressBar Type="ProgressType.Circular" Value="70" Minimum="0" Maximum="100"
TrackThickness="8" ProgressThickness="8">
</SfProgressBar>
```

![progress bar](images/circular.png)