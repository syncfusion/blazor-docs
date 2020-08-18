# Bubbles

Bubbles in the Maps component represent the underlying data values of the maps. Bubbles are scattered throughout the map shapes that contain bound values.

To add bubbles to the maps, bind data source to [`MapsBubble`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsBubbleSettings_members.html), and set [`ValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsBubble~ValuePath.html) as `Population`. The following code example demonstrates how to enable bubbles for the World map with data source.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   DataSource="PopulationDetails"
                   ShapeDataPath="Name"
                   ShapePropertyPath='@("name")'>
            @* To add bubbles based on population count *@
            <MapsBubbleSettings>
                <MapsBubble Visible="true" ValuePath="Population" DataSource="PopulationDetails">
                </MapsBubble>
            </MapsBubbleSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>

@code{
    public class Country
    {
        public string Name;
        public double Population;
    };
    private List<Country> PopulationDetails = new List<Country> {
       new Country
       {
           Name ="United States",
           Population = 325020000
       },
       new Country
       {
           Name = "Russia",
           Population = 142905208
       },
       new Country
        {
           Name="India",
           Population=1198003000
        }
    };
}
```

![Maps with bubbles](./images/Bubble/Bubble.png)

## Bubble sizing

Using the [`MinRadius`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsBubble~MinRadius.html) and [`MaxRadius`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsBubble~MaxRadius.html) properties in [`MapsBubble`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsBubble_members.html), you can render the bubbles in different sizes based on the [`ValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsBubble~ValuePath.html) and [`DataSource`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsBubble~DataSource.html) values.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   ShapePropertyPath='@("name")'
                   DataSource="PopulationDetails"
                   ShapeDataPath="Name">
            @* To add different size of bubbles based on population density *@
            <MapsBubbleSettings>
                <MapsBubble Visible="true"
                            MinRadius="5"
                            MaxRadius="80"
                            ValuePath="PopulationDensity"
                            DataSource="@populationDetails">
                </MapsBubble>
            </MapsBubbleSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> Refer [code block](#bubbles) to know the property value of `PopulationDetails`.

![Maps with different size bubbles](./images/Bubble/population-density.png)

## Multiple bubble groups

You can specify multiple types of bubble groups using the [`MapsBubble`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsBubble_members.html) property and customize it according to your requirement.

In the following code example, the gender-wise population ratio is demonstrated with two different bubble groups.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   ShapePropertyPath='@("name")'
                   DataSource="GenderRatios"
                   ShapeDataPath="Country">
            @* To add multiple bubble groups *@
            <MapsBubbleSettings>
                <MapsBubble Visible="true"
                            MinRadius="5"
                            MaxRadius="20"
                            ValuePath="FemaleRatio"
                            ColorValuePath="FemaleRatioColor"
                            DataSource="GenderRatios">
                </MapsBubble>
                <MapsBubble Visible="true"
                            BubbleType="BubbleType.Circle"
                            Opacity="0.4"
                            MinRadius="15"
                            MaxRadius="25"
                            ValuePath="MaleRatio"
                            ColorValuePath="MaleRatioColor"
                            DataSource="GenderRatios">
                </MapsBubble>
            </MapsBubbleSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>

@code{
    public class GenderRatio
    {
        public string Country;
        public double FemaleRatio;
        public double MaleRatio;
        public string FemaleRatioColor;
        public string MaleRatioColor;
    }

    private List<GenderRatio> GenderRatios = new List<GenderRatio> {
        new GenderRatio {
            Country ="United States",
            FemaleRatio =50.50442726,
            MaleRatio =49.49557274,
            FemaleRatioColor ="green",
            MaleRatioColor = "blue"
        },
        new GenderRatio {
            Country ="India",
            FemaleRatio =48.18032713,
            MaleRatio =51.81967287,
            FemaleRatioColor ="blue",
            MaleRatioColor = "#c2d2d6"
        },
        new GenderRatio {
            Country ="Oman",
            FemaleRatio =34.15597234,
            MaleRatio =65.84402766,
            FemaleRatioColor ="#09156d",
            MaleRatioColor="orange"
        },
        new GenderRatio {
            Country ="United Arab Emirates",
            FemaleRatio =27.59638942,
            MaleRatio =72.40361058,
            FemaleRatioColor ="#09156d",
            MaleRatioColor="orange"
        }
    };
}
```

![Maps with bubble groups](./images/Bubble/Bubble-group.png)

## Enabling legend for bubble

To enable the legends for bubbles, set [`Visible`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsBubble~Visible.html) to true and set [`Type`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.LegendType.html) to [`Bubbles`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.LegendType.html) in [`MapsLegendSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLegendSettings_members.html).

The following code example demonstrates how to enable the legends for bubbles with each bubble different colors rendering.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    @* To enable legend for bubbles *@
    <MapsLegendSettings Visible="true" Type="LegendType.Bubbles"></MapsLegendSettings>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   DataSource="PopulationDetails"
                   ShapeDataPath="Name"
                   ShapePropertyPath='@("name")'>
            <MapsBubbleSettings>
                <MapsBubble Visible="true"
                            ValuePath="Population"
                            ColorValuePath="Color"
                            DataSource="PopulationDetails">
                </MapsBubble>
            </MapsBubbleSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> Refer [code block](#bubbles) to know the property value of `PopulationDetails`.

![Maps with bubble and legend](./images/Bubble/bubblelegend.png)

> Please refer to [legend section](legend) for more information on legend settings.