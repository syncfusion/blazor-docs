<!-- markdownlint-disable MD040 -->

# Getting Started with Blazor WebAssembly Charts Using Visual Studio

This article provides a step-by-step instructions to configure Syncfusion Blazor Charts in a simple Blazor WebAssembly application using Visual Studio 2019.

**Note:** Starting with version 17.4.0.39 (2019 Volume 4), you need to include a valid license key (either paid or trial key) within your applications. Please refer to this help topic for more information.

## Prerequisites

• Visual Studio 2019
• NET Core SDK 3.1.3

**Note:** .NET Core SDK 3.1.3 requires Visual Studio 2019 16.6 or later.

**Note:** Syncfusion Blazor components are compatible with .NET Core 5.0 Preview 6 and it requires Visual Studio 16.7 Preview 1 or later.

## Create a Blazor WebAssembly project in Visual Studio 2019

1. Install the essential project templates in the Visual Studio 2019 by running the below command line in the command prompt.

    ```csharp
    dotnet new -i Microsoft.AspNetCore.Components.WebAssembly.Templates::3.2.0-rc1.20223.4
    ```

2. Choose Create a new project from the Visual Studio dashboard.

    ![chart](../images/getting-started/createproject.png)

3. Select Blazor App from the template and click Next button.

    ![chart](../images/getting-started/blazorapp.png)

4. Now, the project configuration window will popup. Click Create button to create a new project with the default project configuration.

    ![chart](../images/getting-started/blazorconfig.png)

5. Choose Blazor WebAssembly App from the dashboard and click Create button to create a new Blazor WebAssembly application. Make sure .NET Core and ASP.NET Core 3.1 is selected at the top.

    ![chart](../images/getting-started/webassembly.png)

`http://172.16.0.76:9797/products/aspnet-core-blazor-razor-components/control/images/grid/blazor-datagrid-high-performance.png`

**Note:** ASP.NET Core 3.1 available in Visual Studio 2019 version.

## Importing Syncfusion Blazor component in the application

1. Now, install Syncfusion.Blazor NuGet package to the newly created application by using the NuGet Package Manager. Right-click the project and select Manage NuGet Packages.

    ![chart](../images/getting-started/nugetconfig.png)

2. Search Syncfusion.Blazor keyword in the Browser tab and install Syncfusion.Blazor NuGet package in the application.

    ![chart](../images/getting-started/nugetinstall.png)

3. The Syncfusion Blazor package will be installed in the project, once the installation process is completed.

4. Open `**~/_Imports.razor` file and import the `Syncfusion.Blazor.**`

    ```csharp
    @using Syncfusion.Blazor
    @using Syncfusion.Blazor.Charts
    ```

5. Open the ~/Program.cs file and register the Syncfusion Blazor Service.

```csharp
using Syncfusion.Blazor;

namespace WebApplication1
{
    public class Program
    {
        public static async Task Main(string[] args)
        {
            ....
            ....
            builder.Services.AddSyncfusionBlazor();
            await builder.Build().RunAsync();
        }
    }
}
```

## Adding Chart component to the application

Now, add the Syncfusion Blazor components in any web page (razor) in the Pages folder. For example, the Chart component is added in the **~/Pages/Index.razor** page.

**Note:** Adding the lodash script is mandatory since we have used it in our chart’s interactive features. The absence of the script will result in console errors.

```csharp
<head>
   <script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.20/lodash.min.js" integrity="sha512-90vH1Z83AJY9DmlWa8WkjkV79yfS2n2Oxhsi2dZbIv0nC4E6m5AbH8Nh156kkM7JePmqD6tcZsfad1ueoaovww==" crossorigin="anonymous"></script>
</head>
```

 in the **HEAD** element of the **~/wwwroot/index.html**

```csharp
<SfChart></SfChart>
```

## Run the application

After successful compilation of your application, the Syncfusion Blazor chart component will render in the web browser.

![chart](../images/getting-started/chart.png)

## Populate Chart With Data

To bind data for the Chart component, you can assign a IEnumerable object to the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_DataSource) property. The list data source can also be provided as an instance of the [`DataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.DataManager.html).

```csharp
public class SalesInfo
    {
        public string Month { get; set; }
        public double SalesValue { get; set; }
    }
public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };
```

Now map the field  `Month` and `Sales` in the data to the [`XName`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~XName.html) and [`YName`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_YName) properties of the series, then set the data to [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_DataSource) property. As we are going to view the data in column chart, set the [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Type) of the chart as `Column`.

```csharp
@using Syncfusion.Blazor.Charts

    <SfChart>
        <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
        <ChartSeriesCollection>
            <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
            </ChartSeries>
        </ChartSeriesCollection>
    </SfChart>

@code {
    public class SalesInfo
    {
        public string Month { get; set;}
        public double SalesValue { get; set;}
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };
}
```

![chart](../images/getting-started/column.png)

## Add Chart and Axis Titles

You can add a title using [`Title`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_DataSource) property to the chart and an axis to provide quick information to the user about the data plotted in the chart.

```csharp
@using Syncfusion.Blazor.Charts

    <SfChart Width="60%" Title="Sales Analysis">
        <ChartPrimaryXAxis Title="Month" ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>

        <ChartPrimaryYAxis Title="Sales in Dollar"></ChartPrimaryYAxis>

        <ChartSeriesCollection>
            <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
            </ChartSeries>
        </ChartSeriesCollection>
    </SfChart>
@code {
    public class SalesInfo
    {
        public string Month { get; set;}
        public double SalesValue { get; set;}
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };
}
```

![chart](../images/getting-started/columntitle.png)

## Add Data Label

You can add data labels to improve the readability of the chart. This can be achieved by setting the `Visible` property to true in the `DataLabel`.

```csharp
@using Syncfusion.Blazor.Charts

    <SfChart Width="60%" Title="Sales Analysis">
        <ChartPrimaryXAxis Title="Month" ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>

        <ChartPrimaryYAxis Title="Sales in Dollar"></ChartPrimaryYAxis>

        <ChartSeriesCollection>
            <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
                <ChartMarker>
                    <ChartDataLabel Visible="true"></ChartDataLabel>
                </ChartMarker>
            </ChartSeries>
        </ChartSeriesCollection>
    </SfChart>
  @code {
    public class SalesInfo
    {
        public string Month { get; set;}
        public double SalesValue { get; set;}
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };
}
```

![chart](../images/getting-started/data-label.png)

## Enable Tooltip

The tooltip is useful when you cannot display information by using the data labels due to space constraints. You can enable tooltip by setting the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartTooltipSettings.html#Syncfusion_Blazor_Charts_ChartTooltipSettings_Enable) property as true in [`TooltipSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_DataSource).

```csharp
@using Syncfusion.Blazor.Charts

    <SfChart Width="60%" Title="Sales Analysis">
        <ChartPrimaryXAxis Title="Month" ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>

        <ChartPrimaryYAxis Title="Sales in Dollar"></ChartPrimaryYAxis>

        <ChartTooltipSettings Enable="true"></ChartTooltipSettings>

        <ChartSeriesCollection>
            <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
            </ChartSeries>
        </ChartSeriesCollection>
    </SfChart>
  @code {
    public class SalesInfo
    {
        public string Month { get; set;}
        public double SalesValue { get; set;}
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };
}
```

![chart](../images/getting-started/tooltip.png)

## Enable Legend

You can use legend for the chart by setting the [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartLegendSettings.html#Syncfusion_Blazor_Charts_ChartLegendSettings_Visible) property to true in [`LegendSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.GridEvents-1.html#Syncfusion_Blazor_Grids_GridEvents_1_QueryCellInfo). The name of the legend can be set by using [`Name`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Name) property in the series.

```csharp
@using Syncfusion.Blazor.Charts

    <SfChart Width="60%" Title="Sales Analysis">
        <ChartPrimaryXAxis Title="Month" ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>

        <ChartPrimaryYAxis Title="Sales in Dollar"></ChartPrimaryYAxis>

        <ChartLegendSettings Visible="true"></ChartLegendSettings>

        <ChartSeriesCollection>
            <ChartSeries DataSource="@Sales" Name="Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
            </ChartSeries>
        </ChartSeriesCollection>
    </SfChart>
@code {
    public class SalesInfo
    {
        public string Month { get; set;}
        public double SalesValue { get; set;}
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };
}
```

![chart](../images/getting-started/legend.png)

>You can find the fully working sample [`here`](https://www.syncfusion.com/downloads/support/directtrac/general/ze/BlazorDocAppChart1351059325.zip).

## See also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/blazor-webassembly-dotnet-cli/)
* [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019 Preview](https://blazor.syncfusion.com/documentation/getting-started/blazor-server-side-visual-studio-2019/?no-cache=1)
* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/blazor-server-side-dotnet-cli/)