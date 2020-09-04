---
title: "Getting Started"
component: "Smith chart"
description: "This section give you an introduction about the Blazor Smith chart."
---

# Getting Started

This section briefly explains how to include a [`Smithchart`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor.Charts.SfSmithchart.html) in your Blazor client-side application. Refer to this [Getting Started with Syncfusion Blazor for Client-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor/) documentation for introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in an application

Install Syncfusion.Blazor NuGet package to an application using the NuGet Package Manager.

> Please ensure to check the **Include prerelease** option for our Beta release.

You can add the client-side resources through CDN link or format NuGet Package in the `<head>` element of the `~/Pages/Host.cshtml` page.

```csharp
<head>
    <environment include="Development">
        <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ej2.min.js" ></script>
     </environment>
</head>
```

## Adding component package to the application

Open the **~/_Imports.razor** file and import the `Syncfusion.Blazor.Charts` package.

```csharp
@using Syncfusion.Blazor.Charts
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

> To enable custom client-side source loading from CRG or CDN. you need to disable resource loading by **AddSyncfusionBlazor(true)** and load the scripts in the **HEAD** element of the **~/Pages/Host.cshtml** page.

```csharp
<head>
    <environment include="Development">
        <script src="https://cdn.syncfusion.com/blazor/17.4.53/syncfusion-blazor.min.js">
        </script>
    </environment>
</head>
```

## Adding Smith Chart component to an application

Now, add the Syncfusion Blazor Smith Chart component in any webpage `razor` in the `pages` folder. For example, the Smith Chart component is added to the `~/Pages/Index.razor` page.

```csharp
<SfSmithchart>
</SfSmithchart>
```

<b>Run the application</b>

After the successful compilation of your application, press F5 to run the application. The Blazor Smith Chart component will be rendered in the web browser as demonstrated in the following screenshot.

   ![Smith chart Sample](./images/browser-output.png)

## Add series to Smith Chart

Smith Chart series can be added in two ways. You can use either [`Points`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor.Charts.SmithchartSeries.html) or [`Datasource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartSeries.html#Syncfusion_Blazor_Charts_SmithchartSeries_DataSource) in the [`SmithchartSeries`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor.Charts.SmithchartSeries.html) tag. Both points and datasource both should be an array of object.

If you add using [`Datasource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartSeries.html#Syncfusion_Blazor_Charts_SmithchartSeries_DataSource) property, additionally you need to specify data source mapping fields using [`Reactance`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartSeries.html#Syncfusion_Blazor_Charts_SmithchartSeries_Reactance) and [`Resistance`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartSeries.html#Syncfusion_Blazor_Charts_SmithchartSeries_Resistance) properties.

In [`Points`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartSeries.html#Syncfusion_Blazor_Charts_SmithchartSeries_Points) case, you don't need to specify mapping fields as like in [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartSeries.html#Syncfusion_Blazor_Charts_SmithchartSeries_DataSource). But data source fields name should be in 'resistance' and 'reactance'.

The following sample demonstrates adding two series to Smith Chart in both ways.

* First series Transmission1 shows dataSource bound series.
* Second series Transmission2 shows points bound series.

```csharp
@using Syncfusion.Blazor.Charts

<SfSmithchart>
    <SmithchartSeriesCollection>
        <SmithchartSeries
            Name="Transmission1"
            Reactance="reactance"
            Resistance="resistance"
            DataSource="FirstTransmissionSeries">
        </SmithchartSeries>
        <SmithchartSeries
            Name="Transmission2"
            Points="SecondTransmissionSeries">
        </SmithchartSeries>
    </SmithchartSeriesCollection>
</SfSmithchart>

@code {
    public class SmithDataSource
    {
        public double resistance;
        public double reactance;
    };
    private List<SmithDataSource> FirstTransmissionSeries = new List<SmithDataSource> {
        new SmithDataSource { resistance= 10, reactance= 25 },
        new SmithDataSource { resistance= 8, reactance= 6 },
        new SmithDataSource { resistance= 6, reactance= 4.5 },
        new SmithDataSource { resistance= 4.5, reactance= 2 },
        new SmithDataSource { resistance= 3.5, reactance= 1.6 },
        new SmithDataSource { resistance= 2.5, reactance= 1.3 },
        new SmithDataSource { resistance= 2, reactance= 1.2 },
        new SmithDataSource { resistance= 1.5, reactance= 1 },
        new SmithDataSource { resistance= 1, reactance= 0.8 },
        new SmithDataSource { resistance= 0.5, reactance= 0.4 },
        new SmithDataSource { resistance= 0.3, reactance= 0.2 },
        new SmithDataSource { resistance= 0.001, reactance= 0.15 }
    };
    private List<SmithDataSource> SecondTransmissionSeries = new List<SmithDataSource> {
        new SmithDataSource { resistance= 20, reactance= -50 },
        new SmithDataSource { resistance= 10, reactance= -10 },
        new SmithDataSource { resistance= 9, reactance= -4.5 },
        new SmithDataSource { resistance= 8, reactance= -3.5 },
        new SmithDataSource { resistance= 7, reactance= -2.5 },
        new SmithDataSource { resistance= 6, reactance= -1.5 },
        new SmithDataSource { resistance= 5, reactance= -1 },
        new SmithDataSource { resistance= 4.5, reactance= -0.5 },
        new SmithDataSource { resistance= 2, reactance= 0.5 },
        new SmithDataSource { resistance= 1.5, reactance= 0.4 },
        new SmithDataSource { resistance= 1, reactance= 0.4 },
        new SmithDataSource { resistance= 0.5, reactance= 0.2 },
        new SmithDataSource { resistance= 0.3, reactance= 0.1 },
        new SmithDataSource { resistance= 0.001, reactance= 0.05 }
    };
}
```

![Smith chart with transmission series](./images/SeriesSMC.png)

## Add title to SmithChart

[`SmithchartTitle`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor.Charts.SmithchartTitle.html) property used to add title for SmithChart. In that [`Text`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartTitle.html#Syncfusion_Blazor_Charts_SmithchartTitle_Text) API used to set text of the title.

```csharp
<SfSmithchart>
    <SmithchartTitle Text="Impedance Transmission">
    </SmithchartTitle>
    <SmithchartSeriesCollection>
        <SmithchartSeries Name="Transmission1" Points="FirstTransmissionSeries">
        </SmithchartSeries>
        <SmithchartSeries Name="Transmission2" Points="SecondTransmissionSeries">
        </SmithchartSeries>
    </SmithchartSeriesCollection>
</SfSmithchart>
```

> Refer [code block](#add-series-to-smith-chart) to know the property value of `FirstTransmissionSeries` and `SecondTransmissionSeries`.

![Smith chart with title](./images/Title.png)

## Enable marker to Smith Chart

To display marker for particular series, need to set the [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartSeriesMarker.html#Syncfusion_Blazor_Charts_SmithchartSeriesMarker_Visible) property to true in [`SmithchartSeriesMarker`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor.Charts.SmithchartSeriesMarker.html). In below sample, marker is enabled for first series only.

```csharp
<SfSmithchart>
    <SmithchartTitle Text="Impedance Transmission">
    </SmithchartTitle>
    <SmithchartSeriesCollection>
        <SmithchartSeries Name="Transmission1" Points="FirstTransmissionSeries">
            <SmithchartSeriesMarker Visible="true"></SmithchartSeriesMarker>
        </SmithchartSeries>
        <SmithchartSeries Name="Transmission2" Points="SecondTransmissionSeries">
        </SmithchartSeries>
    </SmithchartSeriesCollection>
</SfSmithchart>
```

> Refer [code block](#add-series-to-smith-chart) to know the property value of `FirstTransmissionSeries` and `SecondTransmissionSeries`.

![Smith chart with marker](./images/marker.png)

## Enable data label to Smith Chart marker

To display data label for particular marker series, need to set [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.CircularGauge.CircularGaugeFontSettings.html#Syncfusion_Blazor_CircularGauge_CircularGaugeFontSettings_FontWeight) property to true in [`SmithchartSeriesDatalabel`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor.Charts.SmithchartSeriesDatalabel.html). In below sample, data label is enabled for first series only.

```csharp
<SfSmithchart>
    <SmithchartTitle Text="Impedance Transmission">
    </SmithchartTitle>
    <SmithchartSeriesCollection>
        <SmithchartSeries Name="Transmission1" Points="FirstTransmissionSeries">
            <SmithchartSeriesMarker Visible="true">
                <SmithchartSeriesDatalabel Visible="true"></SmithchartSeriesDatalabel>
            </SmithchartSeriesMarker>
        </SmithchartSeries>
        <SmithchartSeries Name="Transmission2" Points="SecondTransmissionSeries">
        </SmithchartSeries>
    </SmithchartSeriesCollection>
</SfSmithchart>
```

> Refer [code block](#add-series-to-smith-chart) to know the property value of `FirstTransmissionSeries` and `SecondTransmissionSeries`.

![Smith chart with data label and marker](./images/datalabel.png)

## Enable legend for Smith Chart

Smith Chart had a legend feature, which is used to denote the correspond series. To enable the legend, set [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartLegendSettingsModel.html#Syncfusion_Blazor_Charts_SmithchartLegendSettingsModel_Visible) property value to true in [`SmithchartLegendSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor.Charts.SmithchartLegendSettings.html).

```csharp
<SfSmithchart>
    <SmithchartLegendSettings Visible='true'></SmithchartLegendSettings>
    <SmithchartTitle Text="Impedance Transmission">
    </SmithchartTitle>
    <SmithchartSeriesCollection>
        <SmithchartSeries Name="Transmission1" Points="FirstTransmissionSeries">
            <SmithchartSeriesMarker Visible="true">
                <SmithchartSeriesDatalabel Visible="true"></SmithchartSeriesDatalabel>
            </SmithchartSeriesMarker>
        </SmithchartSeries>
        <SmithchartSeries Name="Transmission2" Points="SecondTransmissionSeries">
        </SmithchartSeries>
    </SmithchartSeriesCollection>
</SfSmithchart>
```

> Refer [code block](#add-series-to-smith-chart) to know the property value of `FirstTransmissionSeries` and `SecondTransmissionSeries`.

![Smith chart with legend](./images/legend.png)

## Enable tooltip for Smith Chart Series

The tooltip is useful when you cannot display information by using the data labels due to space constraints. You can enable tooltip by setting the [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SmithchartSeriesTooltip.html#Syncfusion_Blazor_Charts_SmithchartSeriesTooltip_Visible) property to true in [`SmithchartSeriesTooltip`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor.Charts.SmithchartSeriesTooltip.html).

```csharp
<SfSmithchart>
    <SmithchartLegendSettings Visible='true'></SmithchartLegendSettings>
    <SmithchartTitle Text="Impedance Transmission">
    </SmithchartTitle>
    <SmithchartSeriesCollection>
        <SmithchartSeries Name="Transmission1" Points="FirstTransmissionSeries">
            <SmithchartSeriesMarker Visible="true">
                <SmithchartSeriesDatalabel Visible="true"></SmithchartSeriesDatalabel>
            </SmithchartSeriesMarker>
            <SmithchartSeriesTooltip Visible='true'>
            </SmithchartSeriesTooltip>
        </SmithchartSeries>
        <SmithchartSeries Name="Transmission2" Points="SecondTransmissionSeries">
        </SmithchartSeries>
    </SmithchartSeriesCollection>
</SfSmithchart>
```

> Refer [code block](#add-series-to-smith-chart) to know the property value of `FirstTransmissionSeries` and `SecondTransmissionSeries`.

![Smith chart with tooltip](./images/tooltip.png)

## See also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor/)

* [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor-server/)

* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor-server/)