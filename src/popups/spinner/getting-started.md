---
title: "Blazor Spinner | Get started with client and server-side"
component: "Spinner"
description: "In this tutorial, you can get started with the Blazor spinner component by creating and showing or hiding it based on specified target using public utility functions."
---

# Getting Started

This section briefly explains how to include a Spinner component in your Blazor Server-side application. You can refer [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019 page](../getting-started/server-side-blazor/) for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in the application

* Install `Syncfusion.Blazor.Spinner` NuGet package to the application by using the `NuGet Package Manager`.

> Please ensure to check the `Include prerelease` option for our Beta release.

* You can add the client-side resources through CDN or from NuGet package in the `<head>` element of the **~/Pages/_Host.cshtml** page.

```html

<head>
    <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
</head>

```

> For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](../../common/how-to/render-blazor-server-app-in-ie/) for more information.

```html

<head>
    <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
</head>

```

## Adding component package to the application

Open **~/_Imports.razor** file and import the `Syncfusion.Blazor.Spinner` package.

```csharp

@using Syncfusion.Blazor.Spinner

```

## Add SyncfusionBlazor service in Startup.cs

Open the **Startup.cs** file and add services required by Syncfusion components using `services.AddSyncfusionBlazor()` method. Add this method in the ConfigureServices function as follows.

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

> To enable custom client side resource loading from CRG or CDN. You need to disable resource loading by  `AddSyncfusionBlazor(true)` and load the scripts in the `<head>` element of the **~/Pages/_Host.cshtml** page.

```html

<head>
    <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js"></script>
</head>

```

## Add Spinner component

To initialize the Spinner component, add the below code to your **Index.razor** view page which is present under **~/Pages** folder.

The Blazor Spinner component is used to display the loading indication with a specified target area while loading.

### Initialization

Import the `Syncufusion.Blazor.Spinner` NuGet package and initialize the Spinner component by adding the spinner as a child of the target element where the spinner needs to be shown.

The following code explains how to initialize a simple Spinner in the Blazor Razor page.

```csharp

@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Spinner

<div>
    <SfButton @onclick="@ClickHandler">Show/Hide Spinner</SfButton>
    <div id="container">
        <SfSpinner @bind-Visible="@VisibleProperty">
        </SfSpinner>
    </div>
</div>

@code{
    private bool VisibleProperty { get; set; } = false;

    private async Task ClickHandler()
    {
        this.VisibleProperty = true;
        await Task.Delay(2000);
        this.VisibleProperty = false;
    }
}

```

## Run the application

After successful compilation of your application, simply press `F5` to run the application.

The output will be as follows.

![Spinner Default](./images/default.png)
