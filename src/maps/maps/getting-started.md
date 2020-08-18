# Getting Started

Syncfusion Blazor Maps component is ideal for rendering maps from GeoJSON data or from other map providers such as OpenStreetMap and Bing Maps. For example, you can render the World map or the United States map and customize it to the desired look using built-in options in the Blazor Maps component.

This section briefly explains how to include maps in your Blazor Server-side application to demonstrate the permanent and non-permanent countries in the United Nations Security council. Refer to the [Getting Started with Syncfusion Blazor for Server-side in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor/) documentation for introduction and configuring common specifications.

## Importing Syncfusion Blazor component in an application

Install Syncfusion.Blazor NuGet package in an application using the **NuGet Package Manager**.

> Please ensure to check the **Include prerelease** option for our Beta release.

## Adding component package to the application

Open the **~/_Imports.razor** file, and import the `Syncfusion.Blazor.Maps` package.

```csharp
@using Syncfusion.Blazor.Maps
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

> To enable custom client-side source loading from CRG or CDN. You need to disable resource loading by **AddSyncfusionBlazor(true)** and load the scripts in the **HEAD** element of the **~/Pages/Host.cshtml** page.

```html
    <head>
        <environment include="Development">
            <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js">
            </script>
        </environment>
    </head>
```

## Adding the Maps component to an application

Now, add the Syncfusion Blazor Maps component in `razor` web page in the `Pages` folder. For example, the Maps component can be added to the ~/Pages/Index.razor page.

```csharp
<SfMaps></SfMaps>
```

Since it does not contain any details related to the shape of a layer, it will not show any shape on the web page.

## Adding GeoJSON data in Maps layer

Bind GeoJSON data to the Maps to render any geometric shape in SVG (Scalable Vector Graphics) for powerful data visualization of shapes. For example, you can render the world map and make desired customizations on it. You can also add any number of layers in the maps.

You can use the [`ShapeData`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLayer~ShapeData.html) property in [`MapsLayer`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLayer_members.html) to load the GeoJSON shape data into the Maps component.

 ```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        @* load shape data *@
        <MapsLayer ShapeData='new {dataOptions= "https://cdn.syncfusion.com/maps/map-data/world-map.json"}'>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

![Map with GeoJSON layer](./images/browser-output.png)

> The "world-map.json" file contains the world map GeoJSON data.

## Bind data source

The [`DataSource`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLayer~DataSource.html) property is used to represent statistical data in the Maps component. Define an list of objects as a data source to the Maps component. This data source will be further used to color the map, display data labels, display tooltips, and more. Assign this to the `DataSource` property in `MapsLayer`.

```csharp
@code {
    private List<UNCouncilCountry> SecurityCouncilDetails = new List<UNCouncilCountry>{
         new UNCouncilCountry { Name= "China", Membership= "Permanent"},
         new UNCouncilCountry { Name= "France", Membership= "Permanent" },
         new UNCouncilCountry { Name= "Russia", Membership= "Permanent"},
         new UNCouncilCountry { Name= "Kazakhstan", Membership= "Non-Permanent"},
         new UNCouncilCountry { Name= "Poland", Membership= "Non-Permanent"},
         new UNCouncilCountry { Name= "Sweden", Membership= "Non-Permanent"},
         new UNCouncilCountry { Name= "United Kingdom", Membership= "Permanent"},
         new UNCouncilCountry { Name= "United States", Membership= "Permanent"},
         new UNCouncilCountry { Name= "Bolivia", Membership= "Non-Permanent"},
         new UNCouncilCountry { Name= "Eq. Guinea", Membership= "Non-Permanent"},
         new UNCouncilCountry { Name= "Ethiopia", Membership= "Non-Permanent"},
         new UNCouncilCountry { Name= "Côte d Ivoire", Membership= "Permanent"},
         new UNCouncilCountry { Name= "Kuwait", Membership= "Non-Permanent"},
         new UNCouncilCountry { Name= "Netherlands", Membership= "Non-Permanent"},
         new UNCouncilCountry { Name= "Peru", Membership= "Non-Permanent"}
    };

    public class UNCouncilCountry
    {
        public string Name;
        public string Membership;
    };
}
```

> United Nations Security Council data is referred from [source](https://en.wikipedia.org/wiki/List_of_members_of_the_United_Nations_Security_Council).

You should also specify the field names in the shape data and data source to the `ShapePropertyPath` and `ShapeDataPath` properties, respectively. These are used to identify the appropriate shapes and match the specific data source values to them.

> Please [refer to the section](populate-data#data-binding) for more information on data binding.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions= "https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   @* To map shape data name field *@
                   ShapePropertyPath='@("name")'
                   DataSource="SecurityCouncilDetails"
                   @* To map data source field *@
                   ShapeDataPath="Name">
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> For example, consider the field names specified in `ShapePropertyPath` and `ShapeDataPath` have the same value: ‘United States’. So corresponding color, data label and tooltip related settings will be applied to the United States shape.

## Apply color mapping

The color mapping feature supports customization of shape colors based on the underlying value of shape received from bound data. Specify the field name from values that have to be compared for the shapes in the [`ColorValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeSettings~ColorValuePath.html) property in [`MapsShapeSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeSettings_members.html).

Specify color and value in [`MapsShapeColorMapping`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeColorMapping_members.html). Here, '#EDB46F' is specified for 'Permanent' and '#F1931B' is specified for 'Non-Permanent'.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions= "https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   ShapePropertyPath='@("name")'
                   DataSource="SecurityCouncilDetails"
                   ShapeDataPath="Name">
            @* color mapping related configuration *@
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Membership">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping Value="Permanent" Color="@("#EDB46F")"></MapsShapeColorMapping>
                    <MapsShapeColorMapping Value="Non-Permanent" Color="@("#F1931B")"></MapsShapeColorMapping>
                </MapsShapeColorMappings>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

![Map with color mapping](./images/Colormap.png)

> Refer [code block](#bind-data-source) to know the property value of `securityCouncilDetails`.

## Add data labels

You can add label text to the shapes in the Maps component using [`MapsDataLabelSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsDataLabelSettings_members.html), and it provides information to users about the shapes.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions= "https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   ShapePropertyPath='@("name")'
                   DataSource="SecurityCouncilDetails"
                   ShapeDataPath="Name">
            @* To add data labels *@
            <MapsDataLabelSettings Visible="true" LabelPath="Name" IntersectionAction="IntersectAction.Hide"></MapsDataLabelSettings>
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Membership">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping Value="Permanent" Color="@("#EDB46F")"></MapsShapeColorMapping>
                    <MapsShapeColorMapping Value="Non-Permanent" Color="@("#F1931B")"></MapsShapeColorMapping>
                </MapsShapeColorMappings>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> Refer [code block](#bind-data-source) to know the property value of `securityCouncilDetails`.

![Map with labels](./images/shape-label.png)

## Add title for Maps

You can add a title using [`MapsTitleSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsTitleSettings_members.html) to the maps to provide quick information to users about the shapes rendered in the maps.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    @* To add title *@
    <MapsTitleSettings Text="Members of the UN Security Council"></MapsTitleSettings>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions= "https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   ShapePropertyPath='@("name")'
                   DataSource="SecurityCouncilDetails"
                   ShapeDataPath="Name">
            <MapsDataLabelSettings Visible="true" LabelPath="Name" IntersectionAction="IntersectAction.Hide"></MapsDataLabelSettings>
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Membership">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping Value="Permanent" Color="@("#EDB46F")"></MapsShapeColorMapping>
                    <MapsShapeColorMapping Value="Non-Permanent" Color="@("#F1931B")"></MapsShapeColorMapping>
                </MapsShapeColorMappings>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> Refer [code block](#bind-data-source) to know the property value of `securityCouncilDetails`.

![Map with title](./images/Title.png)

## Enable legend

The legend items are used to denote color mapping categories, and you can show legend for the maps by setting true to the [`Visible`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLegendSettings~Visible.html) property in [`MapsLegendSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLegendSettings_members.html).

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsTitleSettings Text="Members of the UN Security Council"></MapsTitleSettings>
    @* To add legend *@
    <MapsLegendSettings Visible="true"></MapsLegendSettings>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions= "https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   ShapePropertyPath='@("name")'
                   DataSource="SecurityCouncilDetails"
                   ShapeDataPath="Name">
            <MapsDataLabelSettings Visible="true" LabelPath="Name" IntersectionAction="IntersectAction.Hide"></MapsDataLabelSettings>
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Membership">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping Value="Permanent" Color="@("#EDB46F")"></MapsShapeColorMapping>
                    <MapsShapeColorMapping Value="Non-Permanent" Color="@("#F1931B")"></MapsShapeColorMapping>
                </MapsShapeColorMappings>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> Refer [code block](#bind-data-source) to know the property value of `securityCouncilDetails`.

![Map with legend](./images/Legend.png)

## Enable tooltip

The tooltip is used when you cannot display information using the data labels due to space constraints.

You can enable tooltip by setting the [`Visible`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.MapsTooltipSettings~Visible.html) property to true in [`MapsLayerTooltipSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.LayerTooltipSettings_members.html).

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsTitleSettings Text="Members of the UN Security Council"></MapsTitleSettings>
    <MapsLegendSettings Visible="true"></MapsLegendSettings>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions= "https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   ShapePropertyPath='@("name")'
                   DataSource="SecurityCouncilDetails"
                   ShapeDataPath="Name">
            <MapsDataLabelSettings Visible="true" LabelPath="Name" IntersectionAction="IntersectAction.Hide"></MapsDataLabelSettings>
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Membership">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping Value="Permanent" Color="@("#EDB46F")"></MapsShapeColorMapping>
                    <MapsShapeColorMapping Value="Non-Permanent" Color="@("#F1931B")"></MapsShapeColorMapping>
                </MapsShapeColorMappings>
            </MapsShapeSettings>
            @* To add tooltip for map shape *@
            <MapsLayerTooltipSettings Visible='true' ValuePath="Name"></MapsLayerTooltipSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> Refer [code block](#bind-data-source) to know the property value of `securityCouncilDetails`.

![Map with tooltip](./images/tooltip.png)

> The [download example](https://www.syncfusion.com/downloads/support/directtrac/general/ze/MapsComponentSamples_(2)-1770509751) shows all syntax and code snippets described on this page.

## See also

* [Getting Started with Syncfusion Blazor for client-side application in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor/)

* [Getting Started with Syncfusion Blazor for server-side application in Visual Studio 2019](https://blazor.syncfusion.com/documentation/getting-started/vs-blazor-server/)

* [Getting Started with Syncfusion Blazor for server-side application in .NET Core CLI](https://blazor.syncfusion.com/documentation/getting-started/dotnet-cli-blazor-server/)
