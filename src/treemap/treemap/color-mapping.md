# Color Mapping

Color mapping is used to customize the color for each group or item based on the specified types of color mappings.

The following options are available to customize the group and leaf items in the TreeMap component.

## Range color mapping

Range color mapping is used to apply color to items by giving specific ranges in the [`DataSource`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap~DataSource.html). You should specify the data source field in the [`RangeColorValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap~RangeColorValuePath.html) property.

The following code example demonstrates how to apply range color mapping.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="Count" TValue="Fruits" DataSource="Fruits" RangeColorValuePath="Count">
    <TreeMapLeafItemSettings LabelPath="FruitName">
        <TreeMapLeafColorMappings>
            <TreeMapLeafColorMapping From="500" To="3000" Color="@("Orange")"></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping From="3000" To="5000" Color="@("Green")"></TreeMapLeafColorMapping>
        </TreeMapLeafColorMappings>
    </TreeMapLeafItemSettings>
</SfTreeMap>

@code {
    //fruits data source
    public class Fruits
    {
        public string FruitName;
        public double Count;
    };
    private List<Fruits> Fruits = new List<Fruits> {
        new Fruits { FruitName="Apple", Count=5000 },
        new Fruits { FruitName="Mango", Count=3000 },
        new Fruits { FruitName="Orange", Count=2300 },
        new Fruits { FruitName="Banana", Count=500 },
        new Fruits { FruitName="Grape", Count=4300 },
        new Fruits { FruitName="Papaya", Count=1200 },
        new Fruits { FruitName="Melon", Count=4500 }
    };
}
```

![TreeMap with color mapping](images/Colormapping/Range.png)

## Equal color mapping

Equal color mapping is used to fill colors to each item by specifying equal value present in the datasource field that can be specified in the [`EqualColorValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap~EqualColorValuePath.html) property.

The following code example demonstrates how to apply equal color mapping.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="Count" TValue="Car" DataSource="Cars" EqualColorValuePath="Brand">
    <TreeMapLeafItemSettings LabelPath="Name">
        <TreeMapLeafColorMappings>
            <TreeMapLeafColorMapping Value="Ford" Color="@("green")"></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping Value="Audi" Color="@("red")"></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping Value="Maruti"  Color="@("orange")"></TreeMapLeafColorMapping>
        </TreeMapLeafColorMappings>
    </TreeMapLeafItemSettings>
</SfTreeMap>

@code {
    // car details
    public class Car
    {
        public string Name;
        public int Count;
        public string Brand;
    };

    private List<Car> Cars = new List<Car> {
        new Car { Name="Mustang", Brand="Ford", Count=232 },
        new Car { Name="EcoSport", Brand="Ford", Count=121 },
        new Car { Name="Swift", Brand="Maruti", Count=143 },
        new Car { Name="Baleno", Brand="Maruti", Count=454 },
        new Car { Name="Vitara Brezza", Brand="Maruti", Count=545 },
        new Car { Name="A3 Cabriolet", Brand="Audi",Count=123 },
        new Car { Name="RS7 Sportback", Brand="Audi", Count=523 }
    };
}
```

![TreeMap with equal color mapping](images/Colormapping/EqualColor.png)

## Desaturation color mapping

Desaturation color mapping is used to apply colors to items with opacity, based on the [`MinOpacity`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.LeafItemSettingsModel~ColorMapping.html) and [`MaxOpacity`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.LeafItemSettingsModel~ColorMapping.html) properties set to the [`ColorMappingModel`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.LeafItemSettingsModel~ColorMapping.html) in the TreeMap component.

The following code example demonstrates how to apply desaturation color mapping.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="Count" TValue="Fruit" DataSource="Fruits" RangeColorValuePath="Count">
    <TreeMapLeafItemSettings LabelPath="Name">
         <TreeMapLeafColorMappings>
            <TreeMapLeafColorMapping From="500" To="3000" MinOpacity="0.2" MaxOpacity="0.5" Color="@("Orange")"></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping From="3000" To="5000" MinOpacity="0.5" MaxOpacity="0.8" Color="@("Green")"></TreeMapLeafColorMapping>
        </TreeMapLeafColorMappings>
    </TreeMapLeafItemSettings>
</SfTreeMap>
```

> Refer [code block](#range-color-mapping) to know the property value of `Fruits`.

![TreeMap with desaturation color mapping](images/Colormapping/Desaturation.png)

## Desaturation with multiple colors

Multiple colors are used to provide gradient effect to specific shapes based on the [`ColorMapping`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.LeafItemSettingsModel~ColorMapping.html) ranges in datasource.

By using the [`Color`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.LeafItemSettingsModel~ColorMapping.html) API, you can set n number of colors.

The following code example demonstrates how to use multiple colors.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="Count" TValue="Fruit" DataSource="Fruits" RangeColorValuePath="Count">
    <TreeMapLeafItemSettings LabelPath="Name">
        <TreeMapLeafColorMappings>
            <TreeMapLeafColorMapping From="500" To="3000" Color='new string[]{ "orange", "pink" }'></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping From="3000" To="5000" Color='new string[]{ "green", "red", "blue" }'></TreeMapLeafColorMapping>
        </TreeMapLeafColorMappings>
    </TreeMapLeafItemSettings>
</SfTreeMap>
```

> Refer [code block](#range-color-mapping) to know the property value of `Fruits`.

![Multiple color mapping in TreeMap with desaturation](images/Colormapping/DesaturationwithMultiplecolor.png)

## Palette color mapping

The palette color mapping is used to fill the same color to each group or leaf node by given colors in the [`Palette`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap~Palette.html) property in the TreeMap component.

The following code example demonstrates how to apply  palette color mapping.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="Count" TValue="Car" DataSource="Cars" Palette='new string[] { "red", "green" }'>
    <TreeMapLeafItemSettings LabelPath="Name">
    </TreeMapLeafItemSettings>
</SfTreeMap>
```

> Refer [code block](#equal-color-mapping) to know the property value of `Cars`.

![TreeMap with palette color mapping](images/Colormapping/Palette.png)

## Color for items excluded from color mapping

Based on the color mapping ranges in data source, get the excluded ranges from color mapping and apply specific color to the items.

The following code example demonstrates how to set the color for items excluded from color mapping.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="Count" TValue="Fruit" DataSource="Fruits" RangeColorValuePath="Count">
    <TreeMapLeafItemSettings LabelPath="Name">
        <TreeMapLeafColorMappings>
            <TreeMapLeafColorMapping From="500" To="3000" Color="@("Orange")"></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping From="3000" To="5000" Color="@("Green")"></TreeMapLeafColorMapping>
            <TreeMapLeafColorMapping Color="@("purple")"></TreeMapLeafColorMapping>
        </TreeMapLeafColorMappings>
    </TreeMapLeafItemSettings>
</SfTreeMap>
```

> Refer [code block](#range-color-mapping) to know the property value of `Fruits`.

![TreeMap color mapping for excluded items](images/Colormapping/ExcludeItem.png)

## Bind the colors to the items from data source

To set color for each item in TreeMap, bind the field name in the datasource to the [`RangeColorValuePath`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap~RangeColorValuePath.html).

The following code example demonstrates how to set the color for TreeMap items.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="Count"
            TValue="Fruit"
            DataSource="Fruits"
            RangeColorValuePath="Count"
            ColorValuePath="Color">
    <TreeMapLeafItemSettings LabelPath="Name"></TreeMapLeafItemSettings>
    <TreeMapLegendSettings visible=true></TreeMapLegendSettings>
</SfTreeMap>

@code {
    public class Fruit
    {
        public string Name;
        public double Count;
        public string Color;
    };

    private List<Fruit> Fruits = new List<Fruit> {
        new Fruit { Name="Apple", Count=5000, Color = "red" },
        new Fruit { Name="Mango", Count=3000, Color="blue" },
        new Fruit { Name="Orange", Count=2300, Color="green" },
        new Fruit { Name="Banana", Count=500 , Color="yellow"},
        new Fruit { Name="Grape", Count=4300 , Color="orange"},
        new Fruit { Name="Papaya",Count=1200 , Color="pink"},
        new Fruit { Name="Melon", Count=4500, Color="violet" }
    };
}
```

![Bind the colors to TreeMap from datasource](images/Colormapping/ColorDS.png)