# Box and Whisker Charts

## Box and Whisker

To render a box and whisker chart, use series[`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Type.html) as `BoxAndWhisker`.
The field y requires n number of data or it should contains minimum of five values to plot a segment.

{% aspTab template="chart/series/other-types/box", sourceFiles="box.razor" %}

{% endaspTab %}

![Box and whisker](../images/othertypes/box.png)

## BoxPlotMode

You can change the rendering mode of the Box and Whisker series using the `BoxPlotMode` property.
The default BoxPlotMode is `Exclusive`.The other BoxPlotMode available are `Inclusive` and `Normal`.

To render a box and whisker chart, use series[`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Type.html) as `BoxAndWhisker`.
The field y requires n number of data or it should contains minimum of five values to plot a segment.

{% aspTab template="chart/series/other-types/box-plot", sourceFiles="box-plot.razor" %}

{% endaspTab %}

![BoxPlotMode](../images/othertypes/box-plot.png)

## ShowMean

In Box and Whisker series `ShowMean` property is used to show the box and whisker average value. The default value of `ShowMean` is false.

{% aspTab template="chart/series/other-types/box-mean", sourceFiles="box-mean.razor" %}

{% endaspTab %}

![ShowMean](../images/chart-types-images/box-mean.png)

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)