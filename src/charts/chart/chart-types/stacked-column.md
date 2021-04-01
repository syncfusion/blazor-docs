# Stacked Column

## Stacked

[`Blazor Stacked Column Chart`](https://www.syncfusion.com/blazor-components/blazor-charts/chart-types/stacked-column-chart) is used to plots data points on top of each other using vertical bars. To render a stacked column series, use series `Type` as `StackingColumn`.

{% aspTab template="chart/series/column-charts/stackedcolumn", sourceFiles="stackedcolumn.razor" %}

{% endaspTab %}

![Stacked Column](../images/chart-types-images/stacked-column.png)

> Note: You can also explore our [`Blazor Stacked Column Chart Example`](https://blazor.syncfusion.com/demos/chart/stacked-column?theme=bootstrap4) to knows how to render and configure the stacking column type chart.

## Customization

You can use the following properties to customize the stacked column series.

* [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Fill.html) – used to change the color of the stacked column.
* [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Opacity) – used to control the transparency of the chart series.
* [``DashArray``](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DashArray.html) – used to render stacked column series with dashes.
* [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Border) – used to render stacked column with border.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>

    <ChartSeriesCollection>
        <ChartSeries DataSource="@DataSource" XName="X" DashArray="5,5" Fill="red" Opacity="0.7" YName="YValue" Type="ChartSeriesType.StackingColumn">
        </ChartSeries>
        <ChartSeries DataSource="@DataSource" XName="X" DashArray="5,5" Fill="blue" Opacity="0.7" YName="YValue" Type="ChartSeriesType.StackingColumn">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>
@code{
    public class ChartData
    {
        public string X { get; set; }
        public double YValue { get; set; }
        public double YValue1 { get; set; }
    }

    public List<ChartData> DataSource = new List<ChartData>
{
        new ChartData { X= "USA", YValue= 46, YValue1=56 },
        new ChartData { X= "GBR", YValue= 27, YValue1=17 },
        new ChartData { X= "CHN", YValue= 26, YValue1=36 },
        new ChartData { X= "UK", YValue= 56,  YValue1=16 },
        new ChartData { X= "AUS", YValue= 12, YValue1=46 },
        new ChartData { X= "IND", YValue= 26, YValue1=16 },
        new ChartData { X= "DEN", YValue= 26, YValue1=12 },
        new ChartData { X= "MEX", YValue= 34, YValue1=32},
    };
}
```

![Custom Stacked Column](../images/chart-types-images/custom-stacked-column.png)

> Note: You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)