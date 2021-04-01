# Chart Series

## Multiple Series

You can add multiple series to the chart by using [`ChartSeries`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html) property. The series are rendered in the order in which they are added to the array of series.

{% aspTab template="chart/series/multiple-series", sourceFiles="multiple-series.razor" %}

{% endaspTab %}

![Multiple Series](images/multiple-series/multiple-series-razor.png)

## Combination Series

Combination of different types like line, column etc, can be rendered in a chart.

>Bar series cannot be combined with any other series as the axis orientation is different from other series.

{% aspTab template="chart/series/combination", sourceFiles="combination.razor" %}

{% endaspTab %}

![Combination Series](images/multiple-series/combination-razor.png)

> Note: You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Legend](./legend)