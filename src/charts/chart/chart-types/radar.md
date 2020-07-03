# Radar Chart

## Radar

To render a radar series, use series [`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Type.html) as `Radar`. To render a line draw type, use series [`DrawType`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~DrawType.html) as `Line`.
[`IsClosed`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~IsClosed.html) property specifies whether to join start and end point of
a line series used in polar chart to form a closed path. Default value of isClosed is true.

{% aspTab template="chart/series/polar_radar/radar-line", sourceFiles="radar-line.razor" %}

{% endaspTab %}

![Line](../images/polar-radar/radar-line-razor.png)

## Customization

### Start Angle

You can customize the start angle of the radar series using
[`StartAngle`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartAxis~StartAngle.html) property. By default, `StartAngle` is 0 degree.

{% aspTab template="chart/series/polar_radar/start-angle", sourceFiles="start-angle.razor" %}

{% endaspTab %}

![Start Angle](../images/polar-radar/start-angle-razor.png)

### Coefficient in axis

You can customize the radius of the radar series using
[`Coefficient`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartAxis~Coefficient.html) property. By default, `Coefficient` is 100.

{% aspTab template="chart/series/polar_radar/co-efficient", sourceFiles="co-efficient.razor" %}

{% endaspTab %}

![Coefficient](../images/polar-radar/co-efficient-razor.png)

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)