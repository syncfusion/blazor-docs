---
title: "Getting Started"
component: "Circular Gauge"
description: "This section explains you the steps required to create a simple Blazor Circular Gauge."
---

# Getting Started

This section briefly explains how to include a Circular Gauge in your Blazor Server-side application. Refer to this [Getting Started with Syncfusion Blazor for Server-side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor/) documentation for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in an application

Install the `Syncfusion.Blazor` NuGet package to the application by using the `NuGet Package Manager`.

> Please Make sure to check the **Include prerelease** option for our Beta release.

## Adding component package to an application

Open the **~/_Imports.razor** file and import the `Syncfusion.Blazor.CircularGauge` package.

```csharp
@using Syncfusion.Blazor.CircularGauge
```

## Add SyncfusionBlazor Service in Startup.cs

Open the **Startup.cs** file and add services required by Syncfusion components using **services.AddSyncfusionBlazor()** method. Add this method in the **ConfigureServices** function as follows.

```csharp
using Syncfusion.Blazor;

namespace BlazorApplication
{
    public class Startup
    {
        ....
        ....
        public void ConfigureServices(IServiceColloection services)
        {
            ....
            ....
            services.AddSyncfusionBlazor();
        }
    }
}
```

> To enable custom client-side resource loading from CRG or CDN. you need to disable resource loading by **AddSyncfusionBlazor(true)** and load the scripts in the **HEAD** element of the **~/Pages/Host.cshtml** page.

```html
    <head>
        <environment include="Development">
            <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js">
            </script>
        </environment>
    </head>
```

## Adding Circular Gauge component to an application

Now, add the Syncfusion Blazor Circular Gauge component in any web page `razor` in the `Pages` folder. For example, the Circular Gauge component is added to the ~/Pages/ Index.razor page.

```csharp
<SfCircularGauge>
</SfCircularGauge>
```

## Run the application

After the successful compilation of your application, press F5 to run the application. The Blazor Circular Gauge component will be rendered in the web browser as shown below.

   ![Circular Gauge Sample](./images/getting-components.png)

## Set pointer value

You can change the pointer value in the above sample using the [`Value`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.CircularGaugePointer~Value.html) property in [`CircularGaugePointer`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.CircularGaugePointer_members.html).

> In Circular Gauge, you can configure multiple axes. On each axis, you can add a pointer.

```csharp
<SfCircularGauge>
    <CircularGaugeAxes>
        <CircularGaugeAxis>
            <CircularGaugePointers>
                <CircularGaugePointer Value="35">
                </CircularGaugePointer>
            </CircularGaugePointers>
        </CircularGaugeAxis>
    </CircularGaugeAxes>
</SfCircularGauge>
```

![Circular Gauge with pointer value](./images/getting-pointer.png)

## See also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor/)

* [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor-server/)

* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor-server/)