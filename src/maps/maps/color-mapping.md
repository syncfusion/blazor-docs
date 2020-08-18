# Color Mapping

Color mapping is used to customize the shape colors based on given values. It has three types: range color mapping, equal color mapping, and desaturation color mapping.

## Range color mapping

Range color mapping is applied by the mapped value, which is a numeric value. Within the given color mapping, ranges are provided in [`DataSource`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLayer~DataSource.html).

Bind the [`DataSource`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLayer~DataSource.html) value and specify the [`ColorValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeSettings~ColorValuePath.html) to 'Density' to map the range value for shapes. Refer to the following code snippets.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/world-map.json"}' DataSource="PopulationDetails" ShapeDataPath="Name" ShapePropertyPath='@("name")'>
            @* To apply color based on density range *@
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Density">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping From="0.00001" To="100" Color='@("yellow")' />
                    <MapsShapeColorMapping From="100" To="400" Color='@("green")' />
                </MapsShapeColorMappings>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>

@code{
    public class PopulationDetail
    {
        public string Code;
        public double Value;
        public string Name;
        public double Population;
        public double Density;
    };
    private List<PopulationDetail> PopulationDetails = new List<PopulationDetail> {
       new PopulationDetail
       {
           Code = "US",
           Value = 34,
           Name ="United States",
           Population = 325020000,
           Density = 33
       },
       new PopulationDetail
       {
           Code ="RU",
           Value = 9,
           Name = "Russia",
           Population = 142905208,
           Density = 8.3
       },
       new PopulationDetail
        {
           Code = "In",
           Value = 384,
           Name="India",
           Population=1198003000,
           Density=364
        },
       new PopulationDetail
       {
           Code="CN",
           Value=143,
           Name="China",
           Population=1389750000,
           Density=144
       }
    };
}
```

![Maps with range color mapping](./images/Colormapping/RangeColor.png)

## Equal color mapping

Equal color mapping is used to apply color mapping if the mapped value is string. The following example demonstrates the permanent and non-permanent countries in the United Nations Security Council in 2017.

Bind the `councilMemberdetails` data to the layer [`DataSource`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLayer~DataSource.html) property, set [`ColorValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeSettings~ColorValuePath.html) to 'Membership' in the [`MapsShapeSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeSettings_members.html), and set the color mapping values to [`MapsShapeColorMapping`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeColorMapping_members.html).

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/world-map.json"}' DataSource="CouncilMemberdetails" ShapeDataPath="Country" ShapePropertyPath='@("name")'>
            @* To apply color based on membership type *@
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Membership">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping Value="Permanent" Color='@("#D84444")' />
                    <MapsShapeColorMapping Value="Non-Permanent" Color='@("#316DB5")' />
                </MapsShapeColorMappings>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>

@code{
    public class UNCouncil
    {
        public string Country;
        public string Membership;
    };
    private List<UNCouncil> CouncilMemberdetails = new List<UNCouncil>{
         new UNCouncil { Country= "China", Membership= "Permanent"},
         new UNCouncil { Country= "France",Membership= "Permanent" },
         new UNCouncil { Country= "Russia",Membership= "Permanent"},
         new UNCouncil { Country= "Kazakhstan",Membership= "Non-Permanent"},
         new UNCouncil { Country= "Poland",Membership= "Non-Permanent"},
         new UNCouncil { Country= "Sweden",Membership= "Non-Permanent"}
    };
}
```

![Maps with equal color mapping](./images/Colormapping/EqualColor.png)

## Desaturation color mapping

Desaturation color mapping is used to apply colors to shapes with opacity based on given values for the [`MinOpacity`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeColorMapping~MinOpacity.html) and [`MaxOpacity`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeColorMapping~MaxOpacity.html) properties in the Maps component.

Bind the `populationDetails` value to the [`DataSource`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLayer~DataSource.html) property, and then specify the [`ColorValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeSettings~ColorValuePath.html) as 'Density' to map the range value for shapes. Refer to the following code examples to apply desaturation color mapping to shapes.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/world-map.json"}' DataSource="PopulationDetails" ShapeDataPath="Name" ShapePropertyPath='@("name")'>
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Density">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping From="100" To="400" Color='@("blue")' MinOpacity="0.3" MaxOpacity="1" />
                </MapsShapeColorMappings>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> Refer [code block](#range-color-mapping) to know the property value of `PopulationDetails`.

![Maps with desaturation color mapping](./images/Colormapping/Desaturation.png)

<b>Desaturation with multiple colors</b>

Multiple colors are used to provide gradient effect to specific shapes based on the ranges in the data source. By using the `Color` property, you can set n number of colors.

Bind the `populationDetails` value to layer [`DataSource`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLayer~DataSource.html) and specify the [`ColorValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsShapeSettings~ColorValuePath.html) as 'Density' to map the range value for shapes. Refer to the following the example for more details.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/world-map.json"}'
                   DataSource="PopulationDetails"
                   ShapeDataPath="Name"
                   ShapePropertyPath='@("name")'>
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Density">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping From="0.00001" To="50" Color='new String[] { "red", "blue"}' />
                    <MapsShapeColorMapping From="50" To="400" Color='new String[] { "green", "yellow"}' />
                </MapsShapeColorMappings>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> Refer [code block](#range-color-mapping) to know the property value of `PopulationDetails`.

![Maps with multi color mapping](./images/Colormapping/DesaturationMultiColor.png)

## Color for items excluded from color mapping

You will map the colors to the shapes based on the ranges or values in the data source. Some data source records may have been excluded from the color mapping configuration, in which case you may also add the color for excluded items.

In following code example, You have added color mapping for the ranges from 0.00001 to 300. If we have any records in the data source beyond this range, color mapping will not be applied. To apply the color for these excluded items, set `Color` value in the `MapsShapeColorMapping` with out range or value.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/world-map.json"}' DataSource="PopulationDetails" ShapeDataPath="Name" ShapePropertyPath='@("name")'>
            <MapsShapeSettings Fill="#E5E5E5" ColorValuePath="Density">
                <MapsShapeColorMappings>
                    <MapsShapeColorMapping From="0.00001" To="100" Color='@("orange")' />
                    <MapsShapeColorMapping From="100" To="300" Color='@("blue")' />
                    @* To apply color for excluded items *@
                    <MapsShapeColorMapping Color="@("green")" />
                </MapsShapeColorMappings>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

> Refer [code block](#range-color-mapping) to know the property value of `PopulationDetails`.

![Color mapping for exculded colors](./images/Colormapping/ExcludeColor.png)