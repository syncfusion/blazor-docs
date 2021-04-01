# 100% Stacked Column

## 100% Stacked

Shows the relative percentage of multiple data series in stacked columns. The cumulative proportion of each stacked column always totals 100%. To render a [`100% stacked column`](https://www.syncfusion.com/blazor-components/blazor-charts/chart-types/100-stacked-column-chart) series, use series [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Type.html) as **StackingColumn100**.

{% aspTab template="chart/series/column-charts/100%stackedcolumn", sourceFiles="stackedcolumn100.razor" %}

{% endaspTab %}

![100% Stacked Column](../images/chart-types-images/stackedcolumn100.png)

> Note: You can also explore our [`Blazor 100% Stacked Column Chart`](https://blazor.syncfusion.com/demos/chart/percent-stacked-column?theme=bootstrap4) Example to knows how to render and configure the 100% stacking column type chart.

## Stacking Group

You can use the [`StackingGroup`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~StackingGroup.html) property to group the stacked columns and 100% stacked columns.
Columns with same group name are stacked on top of each other.

{% aspTab template="chart/series/column-charts/group", sourceFiles="group.razor" %}

{% endaspTab %}

## Customization

You can use the following properties to customize the 100% stacked column series.

* [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Fill.html) – used to change the color of the 100% stacked column.
* [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Opacity) – used to control the transparency of the chart series.
* [``DashArray``](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DashArray.html) – used to render 100% stacked column series with dashes.
* [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Border) – used to render 100% stacked column with border.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>

    <ChartSeriesCollection>
        <ChartSeries DataSource="@DataSource" StackingGroup="Asia" XName="X" DashArray="5,5" Fill="red" Opacity="0.7" YName="YValue" Type="ChartSeriesType.StackingColumn100">
        </ChartSeries>
        <ChartSeries DataSource="@DataSource" StackingGroup="Asia" XName="X" DashArray="5,5" Fill="blue" Opacity="0.7" YName="YValue" Type="ChartSeriesType.StackingColumn100">
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

![Custom 100% Stacked Column](../images/chart-types-images/custom-stacked-column-100.png)

> Note: You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)