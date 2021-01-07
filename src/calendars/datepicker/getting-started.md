---
title: "Getting Started"
component: "DatePicker"
description: "Explains how to get started with the date picker component with its key features such as restrict the date selection, validation, strict mode, and more"
---

# Getting Started

This section briefly explains how to include a **DatePicker** Component in your Blazor client-side application. You can refer to the [Getting Started with Syncfusion Blazor for Client-side in Visual Studio 2019](../getting-started/blazor-webassembly/) page for introduction and configure the common specifications.

To get start quickly with Blazor DatePicker component, you can check on this video.

`youtube:ZN0zSIU59nY`

## Importing Syncfusion Blazor component in the application

* Install `Syncfusion.Blazor.Calendars` NuGet package to the application by using the `NuGet Package Manager`.

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

## Adding DatePicker component to the application

To initialize the DatePicker component add the below code to your `Index.razor` view page which is present under `~/Pages` folder.

The following code shows a basic DatePicker component.

```csharp
<SfDatePicker TValue="DateTime?" Placeholder='Choose a Date'></SfDatePicker>
```

## Run the application

After the successful compilation of your application, press `F5` to run the application.

The output will be as follows.

![DatePicker](./images/default.png)

## Setting the Value and Min and Max dates

The following example demonstrates how to set the [Value](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Calendars.CalendarBase-1.html#Syncfusion_Blazor_Calendars_CalendarBase_1_Value) and [Min](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Calendars.SfDatePicker-1.html) and [Max](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Calendars.CalendarBase-1.html#Syncfusion_Blazor_Calendars_CalendarBase_1_Max) dates on initializing the
DatePicker. Here, you can select a date within the range from 5th to 27th of this month. `TValue` specifies the type of the DatePicker component.

```csharp
<SfDatePicker TValue="DateTime?" Value='@DateValue' Min='@MinDate' Max='@MaxDate'></SfDatePicker>

@code {
    public DateTime? DateValue {get;set;} = new DateTime(DateTime.Now.Year,DateTime.Now.Month,10);
    public DateTime MinDate {get;set;} = new DateTime(DateTime.Now.Year,DateTime.Now.Month,05);
    public DateTime MaxDate {get;set;} = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 27);
}
```

The output will be as follows.

![DatePicker](./images/min_max.png)

## See Also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](../getting-started/dotnet-cli-blazor/)
* [Getting Started with Syncfusion Blazor for Server-side in Visual Studio 2019](../getting-started/vs-blazor-server/)
* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](../getting-started/dotnet-cli-blazor-server/)
