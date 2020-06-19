# High Low Open Close

HiloOpenClose series is used to represent the low, high, open and closing values over time.
To render a HiloOpenClose series, use series [`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Type.html) as `HiloOpenClose`.

HiloOpenClose series requires 5 fields (x, high, low, open and close) to show the high, low, open and close price
values in the stock.

{% aspTab template="chart/series/financial-charts/hilo-openclose", sourceFiles="hilo-openclose.razor" %}

{% endaspTab %}

## Customization of HiloOpenClose Series

In HiloOpenClose series, [`BullFillColor`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~BullFillColor.html) is used to fill the
 segment when the open value is greater than the close value and
[`BearFillColor`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~BearFillColor.html) is used to fill the segment when the open
value is less than the close value.

By default, BullFillColor is set as red and BearFillColor is set as green.

{% aspTab template="chart/series/financial-charts/custom-openclose", sourceFiles="custom-openclose.razor" %}

{% endaspTab %}

![Customization](../images/financial-types/custom.png)

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)