# Leaf Item

A leaf item defines a visualized data element. The leaf item do not contain child nodes, but contains parent node if it specifies the levels in TreeMap. The leaf nodes can be customized.

## Customization

You can customize the leaf item related settings using [`TreeMapLeafItemSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings.html) tag. Following properties are available in the [`TreeMapLeafItemSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings.html)
* [`LabelPath`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings~_labelPath.html) - label is represented by item name or value property name, that is available in data source.
* [`Fill`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings~_fill.html) - Specifies fill color for leaf items
* [`Opacity`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings~_opacity.html) - Specifies opacity of the leaf item fill color
* [`Padding`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings~_padding.html) - Specifies padding of the leaf items
* [`TreeMapLeafLabelStyle`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafLabelStyle.html) - To customize the label color, opacity, font size, font family, font weight, font style
* [`TreeMapLeafBorder`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafBorder.html) - Specifies leaf item border color and width

In following example, 'CountryName' field is mapped to [`LabelPath`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings~_labelPath.html) property, So corresponding country name will be displayed in the label.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap DataSource="GrowthReports"
            TValue="GDPReport"
            WeightValuePath="GDP">
    <TreeMapLeafItemSettings LabelPath="CountryName">
        <TreeMapLeafLabelStyle Color="#000000"></TreeMapLeafLabelStyle>
        <TreeMapLeafBorder Color="#000000" Width="0.5"></TreeMapLeafBorder>
    </TreeMapLeafItemSettings>
</SfTreeMap>

@code{
    public class GDPReport
    {
        public string CountryName;
        public double GDP;
        public double Percentage;
        public int Rank;
    };

    private List<GDPReport> GrowthReports = new List<GDPReport> {
            new GDPReport {CountryName="United States", GDP=17946, Percentage=11.08, Rank=1},
            new GDPReport {CountryName="China", GDP=10866, Percentage= 28.42, Rank=2},
            new GDPReport {CountryName="Japan", GDP=4123, Percentage=-30.78, Rank=3},
            new GDPReport {CountryName="Germany", GDP=3355, Percentage=-5.19, Rank=4},
            new GDPReport {CountryName="United Kingdom", GDP=2848, Percentage=8.28, Rank=5},
            new GDPReport {CountryName="France", GDP=2421, Percentage=-9.69, Rank=6},
            new GDPReport {CountryName="India", GDP=2073, Percentage=13.65, Rank=7},
            new GDPReport {CountryName="Italy", GDP=1814, Percentage=-12.45, Rank=8},
            new GDPReport {CountryName="Brazil", GDP=1774, Percentage=-27.88, Rank=9},
            new GDPReport {CountryName="Canada", GDP=1550, Percentage=-15.02, Rank=10}
    };
}
```

![TreeMap with leaf item](images/LeafItem/LeafLabel.png)

<!-- markdownlint-disable MD036 -->

**Label position and format**

You can position the labels using the [`LabelPosition`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.LabelPosition.html) property and format the text by specifying data values using the [`LabelFormat`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings~LabelFormat.html) property.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap DataSource="GrowthReports"
            TValue="GDPReport"
            WeightValuePath="GDP">
    <TreeMapLeafItemSettings LabelPath="CountryName"
                             LabelPosition="LabelPosition.TopCenter"
                             LabelFormat="${CountryName}<br>$${GDP} Trillion<br>(${Percentage} %)">
        <TreeMapLeafLabelStyle Color="#000000"></TreeMapLeafLabelStyle>
        <TreeMapLeafBorder Color="#000000" Width="0.5"></TreeMapLeafBorder>
    </TreeMapLeafItemSettings>
</SfTreeMap>
```

> Refer [code block](#customization) to know the property value of `GrowthReports`.

![TreeMap with label position and format](images/LeafItem/LabelFormat.png)

## Gap between the leaf items

The [`Gap`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLeafItemSettings~Gap.html) property is used to separate an item from another item. Each item rectangle is split into equal space with specified gap.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap DataSource="GrowthReports"
            TValue="GDPReport"
            WeightValuePath="GDP">
    <TreeMapLeafItemSettings LabelPath="CountryName" Gap="20">
    </TreeMapLeafItemSettings>
</SfTreeMap>
```

> Refer [code block](#customization) to know the property value of `GrowthReports`.

![Gap in TreeMap item](images/LeafItem/itemgap.png)