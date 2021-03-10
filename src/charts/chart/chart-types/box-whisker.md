# Box and Whisker Charts

## Box and Whisker

To render a [`box and whisker chart`](https://www.syncfusion.com/blazor-components/blazor-charts/chart-types/box-and-whisker-chart), use series[`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Type.html) as `BoxAndWhisker`.
The field y requires n number of data or it should contains minimum of five values to plot a segment.

{% aspTab template="chart/series/other-types/box", sourceFiles="box.razor" %}

{% endaspTab %}

![Box and whisker](../images/othertypes/box.png)

**New Note:** You can also explore our [`Blazor Box and Whisker Chart`](https://blazor.syncfusion.com/demos/chart/box-and-whisker) example to knows how to render and configure the box and whisker type charts.

## BoxPlotMode

You can change the rendering mode of the Box and Whisker series using the `BoxPlotMode` property.
The default BoxPlotMode is `Exclusive`.The other BoxPlotMode available are `Inclusive` and `Normal`.

To render a box and whisker chart, use series[`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Type.html) as `BoxAndWhisker`.
The field y requires n number of data or it should contains minimum of five values to plot a segment.

{% aspTab template="chart/series/other-types/box-plot", sourceFiles="box-plot.razor" %}

{% endaspTab %}

![BoxPlotMode](../images/othertypes/box-plot.png)

## ShowMean

In Box and Whisker series `ShowMean` property is used to show the box and whisker average value. The default value of `ShowMean` is false.

{% aspTab template="chart/series/other-types/box-mean", sourceFiles="box-mean.razor" %}

{% endaspTab %}

![ShowMean](../images/chart-types-images/box-mean.png)

**New Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)