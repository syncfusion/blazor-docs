---
title: " Chart Marker | ASP.NET Core Blazor "

component: "Chart"

description: "Data markers are used to provide information about the data points in the series. You can add a shape to adorn each data point."
---

# Data Markers

Data markers are used to provide information about the data points in the series. You can add a shape to adorn each data point.

<!-- markdownlint-disable MD036 -->

## Marker

<!-- markdownlint-disable MD036 -->

Markers can be added to the points by enabling the [`Visible`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Marker.html)
option of the marker property.

{% aspTab template="chart/data-marker/marker", sourceFiles="marker.razor" %}

{% endaspTab %}

![Marker](images/marker/marker-razor.png)

## Shape

Markers can be assigned with different shapes such as Rectangle, Circle, Diamond etc using the [`Shape`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.ChartCommonMarkerSettings~Shape.html) property.

{% aspTab template="chart/data-marker/shape", sourceFiles="shape.razor" %}

{% endaspTab %}

![Shape](images/marker/shape-razor.png)

>Note : To know more about the marker shape type refer the [`Shape`](https://help.syncfusion.com/cr/cref_files/aspnetmvc-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartMarkerSettings~Shape.htmlg).

## Images

Apart from the shapes, you can also add custom images to mark the data point using the
[`ImageUrl`](https://help.syncfusion.com/cr/cref_files/aspnetmvc-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartMarkerSettings~ImageUrl.html) property.

{% aspTab template="chart/data-marker/images", sourceFiles="images.razor" %}

{% endaspTab %}

## Customization

Marker's color and border can be customized using `Fill` and `Border` properties.

{% aspTab template="chart/data-marker/custom", sourceFiles="custom.razor" %}

{% endaspTab %}

![Customization](images/marker/custom-razor.png)

## See Also

* [Tooltip](./tool-tip)
* [Legend](./legend)