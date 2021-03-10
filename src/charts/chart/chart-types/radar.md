# Radar Chart

## Radar

To render a radar series, use series [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Type.html) as `Radar`. To render a line draw type, use series [`DrawType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DrawType.html) as `Line`.
[`IsClosed`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~IsClosed.html) property specifies whether to join start and end point of
a line series used in polar chart to form a closed path. Default value of isClosed is true.

{% aspTab template="chart/series/polar_radar/radar-line", sourceFiles="radar-line.razor" %}

{% endaspTab %}

![Line](../images/polar-radar/radar-line-razor.png)

**New Note:** You can refer to our [`Blazor Radar Chart`](https://www.syncfusion.com/blazor-components/blazor-charts/chart-types/radar-chart) feature tour page to know about its other groundbreaking feature representations. You can also explore our [`Blazor Radar Chart Example`](https://blazor.syncfusion.com/demos/chart/polar-line?theme=bootstrap4) to know how to render radar series and line draw type.

## Customization

### Start Angle

You can customize the start angle of the radar series using
[`StartAngle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~StartAngle.html) property. By default, `StartAngle` is 0 degree.

{% aspTab template="chart/series/polar_radar/start-angle", sourceFiles="start-angle.razor" %}

{% endaspTab %}

![Start Angle](../images/polar-radar/start-angle-razor.png)

### Coefficient in axis

You can customize the radius of the radar series using
[`Coefficient`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~Coefficient.html) property. By default, `Coefficient` is 100.

{% aspTab template="chart/series/polar_radar/co-efficient", sourceFiles="co-efficient.razor" %}

{% endaspTab %}

![Coefficient](../images/polar-radar/co-efficient-razor.png)

**New Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)