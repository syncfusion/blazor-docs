---
title: "Blazor Toast Notification | Get started from client-side"
component: "Toast"
description: "This section explains the step-by-step process to get started with Blazor toast notification using Blazor client-side application in Visual Studio 2019."
---
<!-- markdownlint-disable MD024 -->

# Getting Started

This section briefly explains how to include a Toast component in your Blazor Server-side application. You can refer [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019 page](../getting-started/server-side-blazor/) for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in the application

* Install `Syncfusion.Blazor` NuGet package to the application by using the `NuGet Package Manager`.

> Please ensure to check the `Include prerelease` option for our Beta release.

* You can add the client-side resources through CDN or from NuGet package in the `<head>` element of the **~/Pages/_Host.cshtml** page.

```html

<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    @*<link href="https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css" rel="stylesheet" />*@
</head>

```

> For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](../../common/how-to/render-blazor-server-app-in-ie/) for more information.

```html

<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
</head>

```

## Adding component package to the application

Open **~/_Imports.razor** file and import the `Syncfusion.Blazor.Notifications` package.

```csharp

@using Syncfusion.Blazor.Notifications

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

## Add Toast component

To initialize the Toast component, add the below code to your **Index.razor** view page which is present under **~/Pages** folder.

The following code explains how to initialize a simple Toast in Razor page.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Notifications
@using Syncfusion.Blazor.Buttons

<SfToast @ref="ToastObj" Title="Adaptive Tiles Meeting" TimeOut=5000 Icon="e-meeting" Content="@ToastContent">
    <ToastPosition X="Right"></ToastPosition>
</SfToast>
<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div id="toastBtnDefault" style="margin: auto;text-align: center">
        <SfButton Content="Show Toasts" @onclick="@ShowOnClick"></SfButton>
        <SfButton Content="Hide All" @onclick="@HideOnClick"></SfButton>
    </div>
</div>

<style>
    #toast_default .e-meeting::before {
        content: "\e705";
        font-size: 17px;
    }
</style>

@code {
    SfToast ToastObj;

    public string ToastContent { get; set;} = "Conference Room 01 / Building 135 10:00 AM-10:30 AM";
    private void ShowOnClick()
    {
        this.ToastObj.Show();
    }
    private void HideOnClick()
    {
        this.ToastObj.Hide("All");
    }

}

```

## Run the application

After successful compilation of your application, run the application.

The output will be as follows.

![Toast Sample](./images/toast.png)

## See Also

* [Getting Started with Syncfusion Blazor for client-side in .NET Core CLI](../getting-started/blazor-webassembly-dotnet-cli/)

* [Getting Started with Syncfusion Blazor for server-side in Visual Studio 2019](../getting-started/server-side-blazor/)

* [Getting Started with Syncfusion Blazor for server-side in .NET Core CLI](../getting-started/server-side-blazor-dotnet-cli/)