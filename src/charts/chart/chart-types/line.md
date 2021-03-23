# Line Charts

## Line

[`Blazor Line Chart`](https://www.syncfusion.com/blazor-components/blazor-charts/chart-types/line-chart) represents and visualizes the time-dependent data to show the trends at equal intervals. To render a line series, use series [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Type) as **Line**.

{% aspTab template="chart/series/line-charts/line", sourceFiles="line.razor" %}

{% endaspTab %}

![Line Charts](../images/chart-types-images/line.png)

## Multicolored Line

To render a multicolored line series, use the series type as `MultiColoredLine`.
Here, the individual colors to the data can be mapped by using [`PointColorMapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~PointColorMapping.html).

{% aspTab template="chart/series/line-charts/multi-line", sourceFiles="multi-line.razor" %}

{% endaspTab %}

![Multicolored Line](../images/chart-types-images/multi-line.png)

## Customization

You can use the following properties to customize the line series.

* [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Fill.html) – used to change the color of the line.
* [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Width.html) – used to change the width of the line.
* [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Opacity.html) – used to control the transparency of the chart series.
* [``DashArray``](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DashArray.html) – used to render line series with dashes.

{% aspTab template="chart/series/line-charts/custom-line", sourceFiles="custom-line.razor" %}

{% endaspTab %}

![Line Charts](../images/chart-types-images/line-cus.png)

> Note: You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)