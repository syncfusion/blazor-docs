---
title: "Getting Started with ASP.NET Core Blazor server-side in Visual Studio 2019"
component: "Card"
description: "This section briefly explains how to create the Card component and configure its available functionalities in Blazor server-side web application and also how to include a simple Card in your Blazor server-side web application"
---

<!-- markdownlint-disable MD040 -->

# Getting Started in Blazor Card

This section briefly explains about how to include a `Card` in your Blazor server-side application. You can refer [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/blazor-webassembly/) page for the introduction and configuring the common specifications.

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
@using Syncfusion.Blazor.Cards
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

## Adding Card component to the application

Now, add the Syncfusion Blazor components in any web page (razor) in the Pages folder. For example, the Card component is added in the **~/Pages/Index.razor** page.

```csharp
<SfCard> Sample Card </SfCard>
```

## Adding a header and content

1. You can create Card with a header in a specific structure. For adding header you can use `CardHeader` tag and in that `Title` and `SubTitle` can be given.

2. Also content will be added by using `CardContent` tag.

```csharp
<div class="control-section">
    <div class="row">
        <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
            <SfCard>
                <CardHeader Title="Debunking Five Data Science Myths" SubTitle="By John Doe | Jan 20, 2018" />
                <CardContent Content="Tech evangelists are currently pounding their pulpits about all things AI, machine learning, analytics—anything that sounds like the future and probably involves lots of numbers. Many of these topics can be grouped under the intimidating term data science." />
            </SfCard>
        </div>
    </div>
</div>
```

## Run the application

After successful compilation of your application, the Syncfusion Blazor Card component will render in the web browser.

![card](images/default.png)