# High Low Open Close

HiloOpenClose series is used to represent the low, high, open and closing values over time.
To render a HiloOpenClose series, use series [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Type.html) as `HiloOpenClose`.

{% aspTab template="chart/series/financial-charts/hilo-openclose", sourceFiles="hilo-openclose.razor" %}

{% endaspTab %}

## Customization of HiloOpenClose Series

In HiloOpenClose series, [`BullFillColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~BullFillColor.html) is used to fill the
 segment when the open value is greater than the close value and
[`BearFillColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~BearFillColor.html) is used to fill the segment when the open
value is less than the close value.

By default, BullFillColor is set as **red** and BearFillColor is set as **green**.

{% aspTab template="chart/series/financial-charts/custom-openclose", sourceFiles="custom-openclose.razor" %}

{% endaspTab %}

![Customization](../images/financial-types/custom.png)

> Note: You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)