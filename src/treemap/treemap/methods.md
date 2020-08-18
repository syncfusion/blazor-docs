# Methods

## Using methods in TreeMap component

You can create object for the treemap component using `@ref` and call the [`Print`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap%601~Print.html) method as shown in the following example.

```csharp
<button @onclick="PrintMap">Print tree map</button>
<SfTreeMap @ref="treemap" @ref:suppressField DataSource="@growthReport"
            WeightValuePath="GDP"
            TValue="Country">
    <TreeMapLeafItemSettings LabelPath="Name" Fill="lightgray">
    </TreeMapLeafItemSettings>
</SfTreeMap>

@code {
    SfTreeMap<Country> treemap;
    void PrintMap()
    {
        treemap.Print();
    }
    class Country
    {
        public string Name;
        public double GDP;
    }
    private List<Country> growthReport = new List<Country> {
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

## Available methods

### Export

Description: Export the current treemap component to different file formats such as PNG, PDF, JPEG and SVG.

Return: void

|   Argument name      |   Description                                       |
|----------------------| ----------------------------------------------------|
|     type             |    Define the export type(PNG, PDF, JPEG and SVG)   |
|     file name        |    Define the file name                             |
|     orientation      |    Define the orientation(horizontal, vertical)     |

### Print

Description: To print the rendered treemap directly.

Return: void

### ResizeOnTreeMap

Description: To handle the window resize event on treemap.

Return: void

|   Argument name      |   Description                              |
|----------------------| -------------------------------------------|
|     pointerEvent        |    Specifies the pointer event            |

### Refresh

Description: The component is rendered again. Whenever you make changes with the treemap properties.

Return: void