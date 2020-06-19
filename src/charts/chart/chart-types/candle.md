# Candle Charts

## Candle

Candle series are similar to Hilo Open Close series, are used to represent the low,
high, open and closing price over time. To render a candle series, use series
[`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Type.html) as `Candle`.

{% aspTab template="chart/series/financial-charts/candle", sourceFiles="candle.razor" %}

{% endaspTab %}

![Candles](../images/financial-types/candles.png)

## Hollow Candles

Candle charts allow to visually compare the current price with previous price by customizing the appearance.

Candles are filled/left as hollow based on the following criteria.

<!-- markdownlint-disable MD033 -->
<table>
<tr>
<td><b>States</b></td>
<td><b>Description </b></td>
</tr>
<tr>
<td>Filled</td>
<td>Candle sticks are filled when the close value is lesser than the open value</td>
</tr>
<tr>
<td>Unfilled</td>
<td>Candle sticks are unfilled when the close value is greater than the open value</td>
</tr>
</table>

The color of the candle will be defined by comparing with previous values.

Bear color  will be applied when the current closing value is greater than the previous closing value.
Bull color will be applied when the current closing value is less than the previous closing value.

By default, BullFillColor is set as red and BearFillColor is set as green.

## Solid Candles

[`EnableSolidCandles`](https://help.syncfusion.com/cr/cref_files/aspnetmvc-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~EnableSolidCandles.html) is used to enable/disable the solid
candles. By default is set to be false. The fill color of the candle will be defined by its opening and closing values.

[`BearFillColor`](https://help.syncfusion.com/cr/cref_files/aspnetmvc-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~BearFillColor.html) will be applied when the opening value is less than the closing value.
[`BullFillColor`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~BullFillColor.html)
will be applied when the opening value is greater than closing value.

{% aspTab template="chart/series/financial-charts/solid-candles", sourceFiles="solid-candles.razor" %}

{% endaspTab %}

![Solid Candles](../images/financial-types/solid-candles.png)

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)