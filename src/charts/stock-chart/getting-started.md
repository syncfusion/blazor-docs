---
title: "Getting Started"
component: "StockChart"
description: "This section briefly explains how to create the StockChart component and configure its available functionalities in a Razor application and also how to include a simple StockChart in Blazor client-side in Visual Studio 2019 Preview application."
---

<!-- markdownlint-disable MD040 -->

# Getting Started

This section briefly explains about how to include a `StockChart` in your Blazor server-side application. You can refer [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/blazor-webassembly/) page for the introduction and configuring the common specifications.

To get start quickly with Blazor stock chart component, you can check on this video.

`youtube:AxnqK2BnapM`

## Importing Syncfusion Blazor component in the application

1. Install **Syncfusion.Blazor** NuGet package to the application by using the NuGet Package Manager. Please ensure to check the **Include prerelease** option.
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
@using Syncfusion.Blazor.Charts
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

## Adding StockChart component to the application

Now, add the Syncfusion Blazor components in any web page (razor) in the Pages folder. For example, the StockChart component is added in the **~/Pages/Index.razor** page.

```csharp
<SfStockChart></SfStockChart>
```

## Populate Stock Chart with Data

To bind data for the Stock Chart component, you can assign a list of items to the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.StockChartSeries~DataSource.html) property. The list can also be provided as an instance of the `DataManager`.

```csharp
public class StockChartData
{
    public DateTime Date;
    public Double Open;
    public Double Low;
    public Double Close;
    public Double High;
    public Double Volume;
}
public List<StockChartData> StockDetails = new List<StockChartData>
    {
        new StockChartData { Date = new DateTime(2012, 04, 02), Open = 85.9757, High = 90.6657, Low = 85.7685, Close = 90.5257, Volume = 660187068},
        new StockChartData { Date = new DateTime(2012, 04, 09), Open = 89.4471, High = 92, Low = 86.2157, Close = 86.4614, Volume = 912634864},
        new StockChartData { Date = new DateTime(2012, 04, 16), Open = 87.1514, High = 88.6071, Low = 81.4885, Close = 81.8543, Volume = 1221746066},
        new StockChartData { Date = new DateTime(2012, 04, 23), Open = 81.5157, High = 88.2857, Low = 79.2857, Close = 86.1428, Volume = 965935749},
        new StockChartData { Date = new DateTime(2012, 04, 30), Open = 85.4, High =  85.4857, Low = 80.7385, Close = 80.75, Volume = 615249365},
        new StockChartData { Date = new DateTime(2012, 05, 07), Open = 80.2143, High = 82.2685, Low = 79.8185, Close = 80.9585, Volume = 541742692},
        new StockChartData { Date = new DateTime(2012, 05, 14), Open = 80.3671, High = 81.0728, Low = 74.5971, Close = 75.7685, Volume = 708126233},
        new StockChartData { Date = new DateTime(2012, 05, 21), Open = 76.3571, High = 82.3571, Low = 76.2928, Close = 80.3271, Volume = 682076215},
        new StockChartData { Date = new DateTime(2012, 05, 28), Open = 81.5571, High = 83.0714, Low = 80.0743, Close = 80.1414, Volume = 480059584},
    };
```

Now set the data to `DataSource` property. By default, stock chart will be rendered based on provided `Date` and `High` value without any mapping.

```csharp
<SfStockChart>
    <StockChartSeriesCollection>
        <StockChartSeries DataSource="@StockDetails" Type="ChartSeriesType.Candle" XName="Date" High="High" Low="Low" Open="Open" Close="Close" Volume="Volume"></StockChartSeries>
    </StockChartSeriesCollection>
</SfStockChart>
```

## Run the application

After successful compilation of your application, the Syncfusion Blazor Stock Chart component will render in the web browser.

![stock chart](images/stock-chart.png)

## Add Stock Chart Title

You can add a title using `Title` property to the Stock Chart to provide quick information to the user about the data plotted in the Chart.

{% aspTab template="stock-chart/getting-started/title", sourceFiles="title.razor" %}

{% endaspTab %}

![StockChart Title](images/title.png)

## Add Crosshair

Crosshair has a vertical and horizontal line to view the value of the axis at mouse or touch position.

Crosshair lines can be enabled by using [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.StockChartCrosshairSettings~Enable.html) property in the [`Crosshair`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsStockChart~Crosshair.html). Likewise tooltip label for an axis can be enabled by using `Enable` property of `CrosshairTooltip` in the corresponding axis.

{% aspTab template="stock-chart/getting-started/crosshair", sourceFiles="crosshair.razor" %}

{% endaspTab %}

![Crosshair](images/crosshair.png)

## Add Trackball

Trackball is used to track a data point closest to the mouse or touch position. Trackball marker indicates the closest point and trackball tooltip displays the information about the point.

Trackball can be enabled by setting the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.StockChartCrosshairSettings~Enable.html) property of the `Crosshair` to true and [`Shared`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.StockChartTooltipSettings~Shared.html) property in `Tooltip` to true in chart.

{% aspTab template="stock-chart/getting-started/trackball", sourceFiles="trackball.razor" %}

{% endaspTab %}

![Trackball](images/trackball.png)

>You can find the fully working sample [`here`](https://www.syncfusion.com/downloads/support/directtrac/general/ze/BlazorApp1286933027.zip).

## See also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/blazor-webassembly-dotnet-cli/)
* [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019 Preview](https://blazor.syncfusion.com/documentation/getting-started/server-side-blazor/?no-cache=1)
* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/server-side-blazor-dotnet-cli/)