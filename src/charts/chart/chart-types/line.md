# Line Charts

## Line

To render a line series, use series [`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Type.html) as `Line`.

{% aspTab template="chart/series/line-charts/line", sourceFiles="line.razor" %}

{% endaspTab %}

![Line Charts](../images/chart-types-images/line.png)

## Multicolored Line

To render a multicolored line series, use the series type as `MultiColoredLine`.
Here, the individual colors to the data can be mapped by using [`PointColorMapping`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.Blazor~Syncfusion.EJ2.Blazor.Charts.ChartSeries~PointColorMapping.html).

{% aspTab template="chart/series/line-charts/multi-line", sourceFiles="multi-line.razor" %}

{% endaspTab %}

![Multicolored Line](../images/chart-types-images/multi-line.png)

## Customization

You can use the following properties to customize the line series.

* [`Fill`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Fill.html) – used to change the color of the line.
* [`Width`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Width.html) – used to change the width of the line.
* [`Opacity`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.Blazor~Syncfusion.EJ2.Blazor.Charts.ChartSeries~Opacity.html) – used to control the transparency of the chart series.
* [``DashArray``](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~DashArray.html) – used to render line series with dashes.

{% aspTab template="chart/series/line-charts/custom-line", sourceFiles="custom-line.razor" %}

{% endaspTab %}

![Line Charts](../images/chart-types-images/line-cus.png)

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)