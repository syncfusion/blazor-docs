# Print and Export

## Print

To use the print functionality, we should set the [`AllowPrint`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap%601~AllowPrint.html) property to **true**. The rendered treemap can be printed directly from the browser by calling the method [`print`]. You can get the TreeMap component object using `@ref="treemap"`.

```csharp
@using Syncfusion.Blazor.TreeMap

<button @onclick="PrintTreeMap">Print</button>
<SfTreeMap @ref="treemap" AllowPrint="true" WeightValuePath="Count" TValue="Fruit" DataSource="Fruits">
    <TreeMapLeafItemSettings LabelPath="Name" Gap="2"></TreeMapLeafItemSettings>
</SfTreeMap>

@code {
    SfTreeMap<Fruit> treemap;
    void PrintTreeMap()
    {
        this.treemap.Print();
    }
    public class Fruit
    {
        public string Name;
        public int Count;
    };

    private List<Fruit> Fruits = new List<Fruit> {
        new Fruit { Name="Apple", Count=5000 },
        new Fruit { Name="Mango", Count=3000 },
        new Fruit { Name="Orange", Count=2300 },
        new Fruit { Name="Banana", Count=500 },
        new Fruit { Name="Grape", Count=4300 },
        new Fruit { Name="Papaya", Count=1200 },
        new Fruit { Name="Melon", Count=4500 }
    };

}
```

![TreeMap with print option](./images/Print/print.png)

## Export

### Image Export

To use the image export functionality, we should set the [`AllowImageExport`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap%601~AllowImageExport.html) property to **true**. The rendered treemap can be exported as an image using the [`export`] method. The method requires two parameters: image type and file name. The treemap can be exported as an image in the following formats.

* JPEG
* PNG
* SVG

```csharp
@using Syncfusion.Blazor.TreeMap

<button @onclick="ExportTreeMap">Export</button>
<SfTreeMap @ref="treemap" AllowImageExport="true" WeightValuePath="Count" TValue="Fruit" DataSource="Fruits">
    <TreeMapLeafItemSettings LabelPath="Name" Gap="2"></TreeMapLeafItemSettings>
</SfTreeMap>

@code {
    SfTreeMap<Fruit> treemap;
    void ExportTreeMap()
    {
        this.treemap.Export(ExportType.PNG, "Treemap");
    }
}
```

> Refer [code block](#print) to know the property value of `Fruits`.

![TreeMap with export option](./images/Print/export.png)

### PDF Export

To use the PDF export functionality, we should set the [`AllowPdfExport`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap%601~AllowPdfExport.html) property to **true**. The rendered treemap can be exported as PDF using the [`export`] method. The [`export`] method requires three parameters: file type, file name and orientation of the PDF document. The orientation setting is optional and "0" indicates portrait and "1" indicates landscape.

```csharp
@using Syncfusion.Blazor.TreeMap

<button @onclick="ExportTreeMap">Export</button>
<SfTreeMap @ref="treemap" AllowPdfExport="true" WeightValuePath="Count" TValue="Fruit" DataSource="Fruits">
    <TreeMapLeafItemSettings LabelPath="Name" Gap="2"></TreeMapLeafItemSettings>
</SfTreeMap>

@code {
    SfTreeMap<Fruit> treemap;
    void ExportTreeMap()
    {
        this.treemap.Export(ExportType.PDF, "Treemap", 0);
    }
}
```

> Refer [code block](#print) to know the property value of `Fruits`.

![TreeMap with export option](./images/Print/export.png)