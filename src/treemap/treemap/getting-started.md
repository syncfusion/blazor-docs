---
title: "Getting Started"
component: "Tree Map"
description: "This section explains you the steps required to create a simple Blazor TreeMap."
---

# Getting Started

This section briefly explains how to include a TreeMap in your Blazor server-side application. Refer to [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor/) documentation for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in an application

Install Syncfusion.Blazor NuGet package in an application using the **NuGet Package Manager**.

> Please ensure to check the **Include prerelease** option for our Beta release.

## Adding component package to an application

Open the **~/_Imports.razor** file and import  `Syncfusion.Blazor.TreeMap`

```csharp
@using Syncfusion.Blazor.TreeMap
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

## Adding TreeMap component to an application

Now, add the Syncfusion Blazor TreeMap component in any web page `razor` in the `Pages` folder. For example, the TreeMap component can be added to the ~/Pages/Index.razor page.

You can use the [`DataSource`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap%601~_dataSource.html) property to load the details car sales details in TreeMap. Specify a field name in the data source in the [`WeightValuePath`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap%601~WeightValuePath.html) property to calculate the TreeMap item size.

```csharp
<SfTreeMap DataSource="GrowthReport"
            WeightValuePath="GDP"
            TValue="Country">
</SfTreeMap>

@code {
    class Country
    {
        public string Name;
        public double GDP;
    }
    private List<Country> GrowthReport = new List<Country> {
        new Country  {Name="United States", GDP=17946 },
        new Country  {Name="China", GDP=10866 },
        new Country  {Name="Japan", GDP=4123 },
        new Country  {Name="Germany", GDP=3355 },
        new Country  {Name="United Kingdom", GDP=2848 },
        new Country  {Name="France", GDP=2421 },
        new Country  {Name="India", GDP=2073 },
        new Country  {Name="Italy", GDP=1814 },
        new Country  {Name="Brazil", GDP=1774 },
        new Country  {Name="Canada", GDP=1550 }
    };
}
```

<b>Run the application</b>

After the successful compilation of your application, press F5 to run the application. The Blazor TreeMap component will render in the web browser as illustrated in the following screenshot.

   ![TreeMap basic sample](images/treemap-basic.png)

## Add labels

You can add label text to the leaf items in TreeMap component using [`LabelPath`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings~_labelPath.html) and it provides information to the user about the leaf items.

```csharp
<SfTreeMap DataSource="GrowthReport"
            WeightValuePath="GDP"
            TValue="Country">
    <TreeMapLeafItemSettings LabelPath="Name" Fill="lightgray"></TreeMapLeafItemSettings>
</SfTreeMap>
```

> Refer [code block](#adding-treemap-component-to-an-application) to know the property value of `GrowthReport`.

![TreeMap with label](images/treemap-with-label.png)

## Add title to TreeMap

You can add a title using [`TreeMapTitleSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap%601~TitleSettings.html) to provide quick information to the user about the items rendered in the TreeMap.

```csharp
<SfTreeMap DataSource="GrowthReport"
            WeightValuePath="GDP"
            TValue="Country">
    <TreeMapTitleSettings Text="Top 10 countries by GDP Nominal - 2015"></TreeMapTitleSettings>
    <TreeMapLeafItemSettings LabelPath="Name" Fill="lightgray"></TreeMapLeafItemSettings>
</SfTreeMap>
```

> Refer [code block](#adding-treemap-component-to-an-application) to know the property value of `GrowthReport`.

![TreeMap with title](images/treemap-with-title.png)

## Apply color mapping

The color mapping feature supports customization of item colors based on the underlying value received from bounded data. Specify the field name from which the values have to be compared for the shapes in [`RangeColorValuePath`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap%601~RangeColorValuePath.html) property in [`SfTreeMap`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap%601.html).

Specify range value and color in [`TreeMapLeafColorMapping`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings~_colorMapping.html). Here 'Orange' is specified for the range '0 - 3000' and 'Green' is specified for the range '3000 - 20000'.

```csharp
<SfTreeMap DataSource="GrowthReport"
            WeightValuePath="GDP"
            TValue="Country"
            RangeColorValuePath="GDP">
    <TreeMapTitleSettings Text="Top 10 countries by GDP Nominal - 2015"></TreeMapTitleSettings>
    <TreeMapLeafItemSettings LabelPath="Name" Fill="lightgray">
        <TreeMapLeafColorMappings>
            <TreeMapLeafColorMapping From="0" To="3000" Color="@("Orange")"></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping From="3000" To="20000" Color="@("Green")"></TreeMapLeafColorMapping>
        </TreeMapLeafColorMappings>
    </TreeMapLeafItemSettings>
</SfTreeMap>
```

> Refer [code block](#adding-treemap-component-to-an-application) to know the property value of `GrowthReport`.

![TreeMap with color mapping](images/Colormapping.png)

## Enable legend

Legend items are used to denote the color mapping categories and you can show legend for the TreeMap by setting true to the [`Visible`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLegendSettings~_visible.html) property in [`TreeMapLegendSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLegendSettings.html).

```csharp
<SfTreeMap DataSource="GrowthReport"
            WeightValuePath="GDP"
            TValue="Country"
            RangeColorValuePath="GDP">
    <TreeMapTitleSettings Text="Top 10 countries by GDP Nominal - 2015"></TreeMapTitleSettings>
    <TreeMapLeafItemSettings LabelPath="Name" Fill="lightgray">
        <TreeMapLeafColorMappings>
            <TreeMapLeafColorMapping From="0" To="3000" Color="@("Orange")"></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping From="3000" To="20000" Color="@("Green")"></TreeMapLeafColorMapping>
        </TreeMapLeafColorMappings>
    </TreeMapLeafItemSettings>
    <TreeMapLegendSettings Visible="true"></TreeMapLegendSettings>
</SfTreeMap>
```

> Refer [code block](#adding-treemap-component-to-an-application) to know the property value of `GrowthReport`.

![TreeMap with legend](images/Legend.png)

## Enable tooltip

The tooltip is useful when you cannot display information by using the data labels due to space constraints. You can enable tooltip by setting the [`Visible`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapTooltipSettings~Visible.html) property as true in [`TreeMapTooltipSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapTooltipSettings~Visible.html).

```csharp
<SfTreeMap DataSource="GrowthReport"
            WeightValuePath="GDP"
            TValue="Country"
            RangeColorValuePath="GDP">
    <TreeMapTitleSettings Text="Top 10 countries by GDP Nominal - 2015"></TreeMapTitleSettings>
    <TreeMapLeafItemSettings LabelPath="Name" Fill="lightgray">
        <TreeMapLeafColorMappings>
            <TreeMapLeafColorMapping From="0" To="3000" Color="@("Orange")"></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping From="3000" To="20000" Color="@("Green")"></TreeMapLeafColorMapping>
        </TreeMapLeafColorMappings>
    </TreeMapLeafItemSettings>
    <TreeMapLegendSettings Visible="true"></TreeMapLegendSettings>
    <TreeMapTooltipSettings Visible="true"></TreeMapTooltipSettings>
</SfTreeMap>
```

> Refer [code block](#adding-treemap-component-to-an-application) to know the property value of `GrowthReport`.

![TreeMap with legend](images/Tooltip.png)

## See also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor/)

* [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor-server/)

* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor-server/)