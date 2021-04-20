# Working with Data

The [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_DataSource) property accepts a collection of values as input that helps to display measures and compares them to a target bar.

## Local Data

Specify the property from the data source in [`ValueField`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_ValueField) and [`TargetField`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_TargetField) to display the measure and target bar.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@LocalChartData" ValueField="Value" TargetField="ComparativeMeasureValue" CategoryField="Category" Height="400" Minimum="0" Maximum="20" Interval="5" Title="Profit in %">
    <BulletChartMinorTickLines Width="0"></BulletChartMinorTickLines>
    <BulletChartRangeCollection>
        <BulletChartRange End=5> </BulletChartRange>
        <BulletChartRange End=15></BulletChartRange>
        <BulletChartRange End=20></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>

@code{
    public class BulletChartData
    {
        public double Value { get; set; }
        public double[] ComparativeMeasureValue { get; set; }
        public string Category { get; set; }
    }
    public List<BulletChartData> LocalChartData = new List<BulletChartData>
    {
        new BulletChartData { Value = 5, ComparativeMeasureValue = new double[] { 7.5 }, Category = "2001" },
        new BulletChartData { Value = 7, ComparativeMeasureValue = new double[] { 5 }, Category = "2002" },
        new BulletChartData { Value = 10, ComparativeMeasureValue = new double[] { 6 }, Category = "2003" },
        new BulletChartData { Value = 5, ComparativeMeasureValue = new double[] { 8 }, Category = "2004" },
        new BulletChartData { Value = 12, ComparativeMeasureValue = new double[] { 5, 6, 9 }, Category = "2005" },
        new BulletChartData { Value = 8, ComparativeMeasureValue = new double[] { 6, 7 }, Category = "2006" }
    };
}
```

![Axis Customization](images/local-data.png)
