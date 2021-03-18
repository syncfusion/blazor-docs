<!-- markdownlint-disable MD040 -->

# Getting Started with Blazor WebAssembly Charts Using Visual Studio

This article provides a step-by-step instructions to configure Syncfusion Blazor Chart in a simple Blazor WebAssembly application using Visual Studio 2019.

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

2. Choose **Create a new project** from the Visual Studio dashboard.

    ![new project in aspnetcore blazor](../images/getting-started/createproject.png)

3. Select **Blazor App** from the template and click Next button.

    ![blazor template](../images/getting-started/blazorapp.png)

4. Now, the project configuration window will popup. Click **Create** button to create a new project with the default project configuration.

    ![asp.net core project configuration](../images/getting-started/blazorconfig.png)

5. Choose **Blazor WebAssembly App** from the dashboard and click **Create** button to create a new Blazor WebAssembly application. Make sure **.NET Core** and **ASP.NET Core 3.1** is selected at the top.

    ![select framework](../images/getting-started/webassembly.png)

    **Note:** ASP.NET Core 3.1 available in Visual Studio 2019 version.

6. Now add the lodash script to the **HEAD** element of the **~/wwwroot/index.html**, since we have used it in our [`chart interactive`]([https://www.syncfusion.com/blazor-components/blazor-charts/interactive-chart]) features. The absence of the script will result in console errors.

    ```html
      <head>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.20/lodash.min.js"></script>
      </head>
    ```

## Importing Syncfusion Blazor component in the application

1. Now, install **Syncfusion.Blazor** NuGet package to the newly created application by using the **NuGet Package Manager**. Right-click the project and select Manage NuGet Packages.

    ![nuget explorer](../images/getting-started/nugetconfig.png)

2. Search **Syncfusion.Blazor** keyword in the Browser tab and install Syncfusion.Blazor NuGet package in the application.

    ![select nuget](../images/getting-started/nugetinstall.png)

3. The Syncfusion Blazor package will be installed in the project, once the installation process is completed.

4. Open `**~/_Imports.razor` file and import the `Syncfusion.Blazor.**`

    ```csharp
    @using Syncfusion.Blazor
    @using Syncfusion.Blazor.Charts
    ```

5. Open the **~/Program.cs** file and register the Syncfusion Blazor Service.

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

## Add Chart Component

To initialize the chart component add the below code to your **Index.razor** view page under **~/Pages** folder. In a new application, if **Index.razor** page has any default content template, then those content can be completely removed and following code can be added.

```csharp
@page "/"

<SfChart>

</SfChart>
```

On successful compilation of your application, the Syncfusion Blazor chart component will render in the web browser.

![chart](../images/getting-started/chart.png)

## Populate Chart with Data

To bind data for the chart component, you can assign a IEnumerable object to the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_DataSource) property. It can also be provided as an instance of the [`DataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.DataManager.html).

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

Now, map the data fields  `Month` and `Sales` to the series [`XName`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_XName) and[`YName`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_YName) properties, and then set the data to the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_DataSource) property.
Set the [`chart type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Type) to `Column` because we will be viewing the data in a column chart.

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

## Add Titles

Using the `Title` property, you can add a title to the chart and the axes to provide the user with quick information about the data plotted in the chart.

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

You can add data labels to improve the readability of the chart. This can be accomplished by setting the DataLabel `Visible` property to **true**.

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

When space constraints prevent you from displaying information using data labels, the tooltip comes in handy. Tooltips can be enabled by setting the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartTooltipSettings.html#Syncfusion_Blazor_Charts_ChartTooltipSettings_Enable) property in [`ChartTooltipSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartTooltipSettings.html) to **true**.

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

You can use legend for the chart by setting the [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartLegendSettings.html#Syncfusion_Blazor_Charts_ChartLegendSettings_Visible) property to **true** in [`ChartLegendSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartLegendSettings.html). The legend name can be changed by using the [`Name`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Name) property in the series.

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

**New Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/blazor-webassembly-dotnet-cli/)
* [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019 Preview](https://blazor.syncfusion.com/documentation/getting-started/blazor-server-side-visual-studio-2019/?no-cache=1)
* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/blazor-server-side-dotnet-cli/)