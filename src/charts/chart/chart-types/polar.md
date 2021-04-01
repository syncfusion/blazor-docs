# Polar Chart

To render a polar series, use series[`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Type.html) as `Polar`.

> Note: You can also explore our [`Blazor Polar Chart example`](https://blazor.syncfusion.com/demos/chart/polar-line) to knows how to render and configure the polar line type charts.

## Draw Types

Polar [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.html) property is used to change the series plotting type to line, column, area, range column, spline,
scatter, stacking area and stacking column. The default value of DrawType is **Line**.

### Line

To render a line draw type, use series [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.html) as **Line**.
[`IsClosed`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~IsClosed.html) property specifies whether to join start and end point of
 a line series used in [`polar chart`](https://www.syncfusion.com/blazor-components/blazor-charts/chart-types/polar-chart) to form a closed path. Default value of isClosed is true.

{% aspTab template="chart/series/polar_radar/polar-line", sourceFiles="polar-line.razor" %}

{% endaspTab %}

![Line](../images/polar-radar/polar-line-razor.png)

### Spline

To render a spline line draw type, use series [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.html) as **Spline**.

{% aspTab template="chart/series/polar_radar/polar-spline", sourceFiles="polar-spline.razor" %}

{% endaspTab %}

![Spline](../images/polar-radar/polar-spline-razor.png)

### Area

To render a area series, use [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.html) as **Area**.

{% aspTab template="chart/series/polar_radar/polar-area", sourceFiles="polar-area.razor" %}

{% endaspTab %}

![Area](../images/polar-radar/polar-area-razor.png)

### Stacked Area

To render a stacked area, use [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.html) as **StackingArea**.

{% aspTab template="chart/series/polar_radar/polar-stackedarea", sourceFiles="polar-stackedarea.razor" %}

{% endaspTab %}

![Stacked Area](../images/polar-radar/polar-stackedarea-razor.png)

### Column

To render a column draw type, use series [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.html) as **Column**.

{% aspTab template="chart/series/polar_radar/polar-column", sourceFiles="polar-column.razor" %}

{% endaspTab %}

![Column](../images/polar-radar/polar-column-razor.png)

### Stacked Column

To render a stacked column draw type, use series [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.html) as `StackingColumn`.

{% aspTab template="chart/series/polar_radar/polar-stackedcolumn", sourceFiles="polar-stackedcolumn.razor" %}

{% endaspTab %}

![Stacked Column](../images/polar-radar/polar-stackedcolumn-razor.png)

### Range Column

To render a range column draw type, use series [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.html) as **RangeColumn**.

{% aspTab template="chart/series/polar_radar/polar-rangecolumn", sourceFiles="polar-rangecolumn.razor" %}

{% endaspTab %}

![Range Column](../images/polar-radar/polar-rangecolumn-razor.png)

### Scatter

To render a scatter draw type, use series [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.htmll) as **Scatter**.

{% aspTab template="chart/series/polar_radar/polar-scatter", sourceFiles="polar-scatter.razor" %}

{% endaspTab %}

![Scatter](../images/polar-radar/polar-scatter-razor.png)

## Customization

### Start Angle

You can customize the start angle of the polar series using
[`StartAngle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~StartAngle.html) property. By default, `StartAngle` is **0 degree**.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartPrimaryXAxis StartAngle="270" ValueType="Syncfusion.Blazor.Charts.ValueType.Category">
    </ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@SalesReports" XName="X" Width="2" YName="Y"
                     Type="ChartSeriesType.Polar" DrawType="ChartDrawType.Line">
            <ChartMarker Height="10" Width="10" Visible="true" Shape="ChartShape.Pentagon"></ChartMarker>
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class ChartData
    {
        public double X { get; set; }
        public double Y { get; set; }
    }

    public List<ChartData> SalesReports = new List<ChartData>
{
        new ChartData{ X= 2005, Y= 28 },
        new ChartData{ X= 2006, Y= 25 },
        new ChartData{ X= 2007, Y= 26 },
        new ChartData{ X= 2008, Y= 27 },
        new ChartData{ X= 2009, Y= 32 },
        new ChartData{ X= 2010, Y= 35 },
        new ChartData{ X= 2011, Y= 30 }
    };
}
```

![Start Angle](../images/polar-radar/polar-start-angle.png)

### Coefficient in axis

You can customize the radius of the polar series using
[`Coefficient`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~Coefficient.html) property. By default, `Coefficient` is **100**.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartPrimaryXAxis Coefficient="40" ValueType="Syncfusion.Blazor.Charts.ValueType.Category">
    </ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@SalesReports" XName="X" Width="2" YName="Y"
                     Type="ChartSeriesType.Polar" DrawType="ChartDrawType.Line">
            <ChartMarker Height="10" Width="10" Visible="true" Shape="ChartShape.Pentagon"></ChartMarker>
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class ChartData
    {
        public double X { get; set; }
        public double Y { get; set; }
    }

    public List<ChartData> SalesReports = new List<ChartData>
{
        new ChartData{ X= 2005, Y= 28 },
        new ChartData{ X= 2006, Y= 25 },
        new ChartData{ X= 2007, Y= 26 },
        new ChartData{ X= 2008, Y= 27 },
        new ChartData{ X= 2009, Y= 32 },
        new ChartData{ X= 2010, Y= 35 },
        new ChartData{ X= 2011, Y= 30 }
    };
}
```

![Coefficient](../images/polar-radar/polar-co-efficient.png)

> Note: You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)