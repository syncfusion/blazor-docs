---
title: "Getting Started with Blazor Progress Bar component | Syncfusion"

component: "Progress Bar"

description: "Learn here about getting started with Syncfusion Blazor Progress Bar (SfProgressBar) component, its elements, and more."
---

# Getting Started with Blazor Progress Bar (SfProgressBar)

This section briefly explains how to include a Progress Bar component in your Blazor server-side application. You can refer to our [Getting Started with Syncfusion Blazor for server-side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/blazor-server-side-visual-studio-2019/) page for introduction and configuring common specifications.

## Importing Syncfusion Blazor Progress Bar component in the application

1. Install **Syncfusion.Blazor** NuGet package to the application by using the **NuGet Package Manager**.

2. You can add the client-side resources through CDN or from NuGet package in the **HEAD** element of the **~/Pages/_Host.cshtml** page.

```html
<head>
    <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
    <!---CDN--->
    @*<link href="https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css" rel="stylesheet" />*@
</head>
```

> For Internet Explorer 11, kindly refer the polyfills. Refer the [documentation](https://blazor.syncfusion.com/blazor/documentation/common/how-to/render-blazor-server-app-in-ie/) for more information.

 ```html
<head>
    <link href="https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css" rel="stylesheet" />
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
</head>
```

## Adding component package to the application

Open the **~/_Imports.razor** file and include the **Syncfusion.Blazor.ProgressBar** namespace.

```csharp
@using Syncfusion.Blazor.ProgressBar
```

## Adding SyncfusionBlazor service in Startup.cs

Open the **Startup.cs** file and add services required by Syncfusion components using **services.AddSyncfusionBlazor()** method. Add this method in the **ConfigureServices** function as follows.

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

> To enable custom client-side source loading from CRG or CDN, please refer to the section about [custom resources in Blazor application](https://blazor.syncfusion.com/documentation/common/custom-resource-generator/#how-to-use-custom-resources-in-the-blazor-application).

## Adding Progress Bar component

To initialize the Progress Bar component, add the below code to your **Index.razor** view page under **~/Pages** folder. In a new application, if **Index.razor** page has any default content template, then those content can be completely removed and following code can be added.

```csharp
@page "/"

<SfProgressBar Value="50" Minimum="0" Maximum="100" TrackThickness="12" ProgressThickness="12">
</SfProgressBar>
```

On successful compilation of your application, the Syncfusion Blazor Progress Bar component will render in the web browser as shown below.

![progress bar](images/linear.png)

## Progress Type

You can change the type of the Progress Bar by using [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressType.html) property. By default [`Linear`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressType.html#Syncfusion_Blazor_ProgressBar_ProgressType_Linear) type of Progress Bar will render. In the below example, you can see the [`Circular`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressType.html#Syncfusion_Blazor_ProgressBar_ProgressType_Circular) type.

```csharp
<SfProgressBar Type="ProgressType.Circular" Value="70" Minimum="0" Maximum="100" TrackThickness="8" ProgressThickness="8">
</SfProgressBar>
```

![progress bar](images/circular.png)
