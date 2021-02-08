---
title: "Getting Started"
component: "Linear Gauge"
description: "This section explains you the steps required to create a simple Blazor Linear Gauge."
---

# Getting Started

This section briefly explains how to include a Linear Gauge in your Blazor Server-Side application. Refer to this [Getting Started with Syncfusion Blazor for Serve-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor/) documentation for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in an application

Install Syncfusion.Blazor NuGet package in application using the **NuGet Package Manager**.

> Please ensure to check the **Include prerelease** option for our Beta release.

## Adding component package to the application

Open the **~/_Imports.razor** file and import the `Syncfusion.Blazor.LinearGauge` package.

```csharp
@using Syncfusion.Blazor.LinearGauge
```

## Adding SyncfusionBlazor Service in Startup.cs

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

> To enable custom client-side source loading from CRG or CDN. you need to disable resource loading by **AddSyncfusionBlazor(true)** and load the scripts in the **HEAD** element of the **~/Pages/Host.cshtml** page

```html
    <head>
        <environment include="Development">
            <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js">
            </script>
        </environment>
    </head>
```

## Adding Linear Gauge component to an application

Now, add the Syncfusion Blazor Linear Gauge component in any web page razor in the Pages folder. For example, the Linear Gauge component is added to the ~/Pages/ Index.razor page.

```csharp
<SfLinearGauge>
</SfLinearGauge>
```

## Run the application

After the successful compilation of your application,  press F5 to run the application. The Blazor Linear Gauge component will be rendered in the web browser as illustrated in the following screenshot.

![Linear Gauge Sample](images/pixel.png)

## Set pointer value

You can change the pointer value in the following sample using the [`Value`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.LinearGaugePointer~_value.html) property in the [`LinearGaugePointer`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.LinearGaugePointer_members.html) tag.

> In Linear Gauge, you can configure multiple axes. On each axis you can add a pointer.

```csharp
@using Syncfusion.Blazor.LinearGauge

<SfLinearGauge>
    <LinearGaugeAxes>
        <LinearGaugeAxis>
            <LinearGaugePointers>
                <LinearGaugePointer Value="40">
                </LinearGaugePointer>
            </LinearGaugePointers>
        </LinearGaugeAxis>
    </LinearGaugeAxes>
</SfLinearGauge>
```

![Linear Gauge with pointer value](images/getting-pointers.png)

## Add Linear Gauge title

You can add title to the linear gauge using [`Title`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.SfLinearGauge~Title.html) property and you can customize this title using following properties.

* [`LinearGaugeTitleStyle`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.LinearGaugeTitleStyle_members.html)
    * [`Color`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGaugeFontSettings~Color.html) - Specifies the title text color
    * [`FontStyle`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGaugeFontSettings~FontStyle.html) - Specifies font style for the title
    * [`FontWeight`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGaugeFontSettings~FontWeight.html) - Specifies font weight for the title
    * [`Size`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGaugeFontSettings~Size.html) - Specifies font size for the title
    * [`Opacity`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGaugeFontSettings~Opacity.html) - Specifies font opacity for the title
    * [`FontFamily`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGaugeFontSettings~FontFamily.html) - Specifies font family for the title

```csharp
@using Syncfusion.Blazor.LinearGauge

<SfLinearGauge Title="Speed calculator">
    <LinearGaugeTitleStyle Color="blue"
                           FontStyle="italic"
                           FontWeight="bold"
                           Size="15px"
                           Opacity="0.8">
    </LinearGaugeTitleStyle>
    <LinearGaugeAxes>
        <LinearGaugeAxis>
            <LinearGaugePointers>
                <LinearGaugePointer Value="40">
                </LinearGaugePointer>
            </LinearGaugePointers>
        </LinearGaugeAxis>
    </LinearGaugeAxes>
</SfLinearGauge>
```

![Linear gauge with title](images/getting-title.png)

## Add axis ranges

You can categorize the axis values using the [`Start`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.LinearGaugeRange~Start.html) and [`End`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.LinearGaugeRange~End.html) properties in the [`LinearGaugeRange`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.LinearGaugeRange_members.html). You can add any number of ranges for an axis using [`LinearGaugeRange`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.LinearGaugeRange_members.html).

```csharp
@using Syncfusion.Blazor.LinearGauge

<SfLinearGauge Title="Speed calculator">
    <LinearGaugeTitleStyle Color="blue"
                           FontStyle="italic"
                           FontWeight="bold"
                           Size="15px"
                           Opacity="0.8">
    </LinearGaugeTitleStyle>
    <LinearGaugeAxes>
        <LinearGaugeAxis>
            <LinearGaugePointers>
                <LinearGaugePointer Value="40">
                </LinearGaugePointer>
            </LinearGaugePointers>
            <LinearGaugeRanges>
                <LinearGaugeRange Start="0" End="30" Color="yellow"></LinearGaugeRange>
                <LinearGaugeRange Start="30" End="60" Color="orange"></LinearGaugeRange>
                <LinearGaugeRange Start="60" End="100" Color="red"></LinearGaugeRange>
            </LinearGaugeRanges>
        </LinearGaugeAxis>
    </LinearGaugeAxes>
</SfLinearGauge>
```

![Linear gauge with range bar](images/getting-ranges.png)

## See also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor/)

* [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor-server/)

* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor-server/)
