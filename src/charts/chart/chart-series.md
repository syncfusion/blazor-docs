---

component: "Chart"

---

# Chart Series

## Multiple Series

You can add multiple series to the chart by using [`ChartSeries`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries.html) property.
The series are rendered in the order as it is added to the series array.

{% aspTab template="chart/series/multiple-series", sourceFiles="multiple-series.razor" %}

{% endaspTab %}

![Multiple Series](images/multiple-series/multiple-series-razor.png)

## Combination Series

Combination of different types like Line, column etc, can be rendered in a chart.

>Bar series cannot be combined with any other series as the axis orientation is different from other series.

{% aspTab template="chart/series/combination", sourceFiles="combination.razor" %}

{% endaspTab %}

![Combination Series](images/multiple-series/combination-razor.png)

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Legend](./legend)