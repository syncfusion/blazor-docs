---
title: "Getting Started"
component: "TextBox"
description: "Helps to get started with the text box component along with its key features such as a floating label, adding icons (input group), and ripple effect."
---

# Getting Started

This section briefly explains how to include a **TextBox** Component in your Blazor client-side application. You can refer to the [Getting Started with Syncfusion Blazor for Client-side in Visual Studio 2019](../getting-started/blazor-webassembly/) page for introduction and configure the common specifications.

To get start quickly with Blazor TextBox component, you can check on this video.

`youtube:vzBKF4Gs-Mc`

## Importing Syncfusion Blazor component in the application

* Install `Syncfusion.Blazor.Inputs` NuGet package to the application by using the `NuGet Package Manager`.

> Please ensure to check the `Include prerelease` option for our Beta release.

* You can add the client-side resources through CDN or from NuGet package in the  **HEAD** element of the **~/Pages/_Host.cshtml** page.

 ```html
    <head>
            <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
            @*<link href="https://cdn.syncfusion.com/blazor/{{version}}/styles/{{theme}}.css" rel="stylesheet" />*@
    </head>
```

> For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](https://ej2.syncfusion.com/blazor/documentation/common/how-to/render-blazor-server-app-in-ie/) for more information.

 ```html
    <head>
        <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
        <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
    </head>
```

## Adding component package to the application

Open `~/_Imports.razor` file and import the `Syncfusion.Blazor.Inputs` packages.

```csharp
@using Syncfusion.Blazor.Inputs
```

## Add SyncfusionBlazor service in Startup.cs

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

> To enable custom client side resource loading from CRG or CDN. You need to disable resource loading by `AddSyncfusionBlazor(true)` and load the scripts in the **HEAD** element of the **~/Pages/_Host.cshtml** page.

 ```html
    <head>
            <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js"></script>
    </head>
```

## Adding TextBox component to the application

To initialize the TextBox component add the below code to your `Index.razor` view page which is present under `~/Pages` folder.

```csharp
<SfTextBox Placeholder='First Name'></SfTextBox>
```

## Run the application

After successful compilation of your application, press `F5` to run the application.

The output will be as follows.

![TextBox Sample](./images/textbox_getting_started.png)

## Adding icons to the TextBox

You can create a TextBox with icon as a group by creating the parent `div` element with the class `e-input-group` and add the icon element as span with the class `e-input-group-icon`.

```csharp
<div class='e-input-group'>
    <input class='e-input' Placeholder='Date of Birth' type='text'>
    <span class='e-input-group-icon e-input-calendar'></span>
</div>

<style>
.e-input-group-icon:before {
  font-family: e-icons;
}

.e-input-group .e-input-group-icon.e-input-calendar {
  font-size: 16px;
}

.e-input-group-icon.e-input-calendar:before {
  content: "";
}
</style>
```

The output will be as follows.

![TextBox with icon](./images/textbox_adding_icons.png)

## Floating label

The floating label TextBox floats the label above the TextBox after focusing, or filled with value in the TextBox. You can create the floating label TextBox by using the `FloatLabelType` API.

```csharp
<SfTextBox Placeholder='First Name' FloatLabelType='@FloatLabelType.Auto'></SfTextBox>
```

The output will be as follows.

![TextBox with icon](./images/floatlabel.png)

## See Also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](../getting-started/dotnet-cli-blazor/)
* [Getting Started with Syncfusion Blazor for Server-side in Visual Studio 2019](../getting-started/vs-blazor-server/)
* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](../getting-started/dotnet-cli-blazor-server/)
