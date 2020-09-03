---
title: "Getting Started"
component: "TimePicker"
description: "Explains how to get started with the time picker component with its key features such as restrict the time selection, validation, strict mode, and more."
---

# Getting Started

This section briefly explains how to include a **TimePicker** Component in your Blazor client-side application. You can refer to the [Getting Started with Syncfusion Blazor for Client-side in Visual Studio 2019](../getting-started/blazor-webassembly/) page for introduction and configure the common specifications.

To get start quickly with Blazor TimePicker component, you can check on this video.

`youtube:X6RsjJIJLIY`

## Importing Syncfusion Blazor component in the application

* Install `Syncfusion.Blazor` NuGet package to the application by using the `NuGet Package Manager`.

> Please ensure to check the `Include prerelease` option for our Beta release.

* You can add the client-side resources through CDN or from NuGet package in the  **HEAD** element of the **~/Pages/_Host.cshtml** page.

 ```html
    <head>
            <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
            @*<link href="https://cdn.syncfusion.com/blazor/{{version}}/styles/{{theme}}.css" rel="stylesheet" />*@
    </head>
```

> For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](https://ej2.syncfusion.com/blazor/documentation/common/how-to/render-blazor-server-app-in-ie/) for more information.

 ```html
    <head>
        <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
        <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
    </head>
```

## Adding component package to the application

Open `~/_Imports.razor` file and import the `Syncfusion.Blazor.Calendars` package.

```csharp
@using Syncfusion.Blazor.Calendars
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

## Adding TimePicker component to the application

To initialize the TimePicker component add the below code to your `Index.razor` view page which is present under `~/Pages` folder.

The following code shows a basic TimePicker component.

```csharp
<SfTimePicker TValue="DateTime?" PlaceHolder="Select a time"></SfTimePicker>
```

## Run the application

After successful compilation of your application, press `F5` to run the application.

The output will be as follows.

![TimePicker](./images/default.png)

## Setting the time format

Time format is a way of representing the time value in different string format in textbox and popup list. By default, the TimePicker’s Format is based on the culture.
But you can customize the Format of the TimePicker using the [Format](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Calendars.SfTimePicker-1.html#Syncfusion_Blazor_Calendars_SfTimePicker_1_Format) property.

The below code demonstrates how to render TimePicker component in 24 hours Format with 60 minutes interval. The time interval is set to 60 minutes by using the [Step](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Calendars.SfTimePicker-1.html#Syncfusion_Blazor_Calendars_SfTimePicker_1_Step) property.

```csharp
<SfTimePicker TValue="DateTime?" Value="@TimeValue" Step=60 Format="HH:mm"></SfTimePicker>

@code {
    public DateTime TimeValue { get; set; } = DateTime.Now;
}
```

The output will be as follows.

![TimePicker](./images/time_format.png)

## See Also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](../getting-started/dotnet-cli-blazor/)
* [Getting Started with Syncfusion Blazor for Server-side in Visual Studio 2019](../getting-started/vs-blazor-server/)
* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](../getting-started/dotnet-cli-blazor-server/)
