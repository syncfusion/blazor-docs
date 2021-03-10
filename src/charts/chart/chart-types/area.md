# Area Charts

## Area

[`Blazor Area Chart`](https://www.syncfusion.com/blazor-components/blazor-charts/chart-types/area-chart) is like line chart to represent time-dependent data and to show the trends at equal intervals, but it fills the area below the line. Uses numeric, category, datetime, or logarithmic axis to plot data. To render a area series, use series `Type` as `Area`.

{% aspTab template="chart/series/area-charts/area", sourceFiles="area.razor" %}

{% endaspTab %}

![Area](../images/chart-types-images/area.png)

**New Note:** You can also explore our [`Blazor Area Chart Example`](https://blazor.syncfusion.com/demos/chart/area?theme=bootstrap4) to knows how to represent time-dependent data, showing trends in data at equal intervals.

## Multicolored area

To render a multicolored area series, use the series type as `MultiColoredArea`.
The required `Segments` of the series can be customized using the `Value`, `Color`, and `DashArray`.

{% aspTab template="chart/series/area-charts/multicolor-area", sourceFiles="multicolor-area.razor" %}

{% endaspTab %}

![Multicolored area](../images/chart-types-images/multicolorarea.png)

## Customization

You can use the following properties to customize the area series.

* [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Fill.html) – used to change the color of the area.
* [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Opacity) – used to control the transparency of the chart series.
* [``DashArray``](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DashArray.html) – used to render area series with dashes.
* `Border` – used to render area series with border.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart Title="Olympic Medals" Width="60%">
    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>

    <ChartSeriesCollection>
        <ChartSeries DataSource="@MedalDetails" XName="X" YName="Y" Opacity="0.5"
                     DashArray="5,5" Fill="blue" Type="ChartSeriesType.Area">
            <ChartSeriesBorder Width="2" Color="red"></ChartSeriesBorder>
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class ChartData
    {
        public string X;
        public double Y;
    }
    public List<ChartData> MedalDetails = new List<ChartData>
{
        new ChartData { X= "South Korea", Y= 39.4 },
        new ChartData { X= "India", Y= 61.3 },
        new ChartData { X= "Pakistan", Y= 20.4 },
        new ChartData { X= "Germany", Y= 65.1 },
        new ChartData { X= "Australia", Y= 15.8 },
        new ChartData { X= "Italy", Y= 29.2 },
        new ChartData { X= "United Kingdom", Y= 44.6 },
        new ChartData { X= "Saudi Arabia", Y= 9.7 },
        new ChartData { X= "Russia", Y= 40.8 },
        new ChartData { X= "Mexico", Y= 31 },
        new ChartData { X= "Brazil", Y= 75.9 },
        new ChartData { X= "China", Y= 51.4 }
    };
}
```

![Area](../images/chart-types-images/area-custom.png)

**New Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)