---
title: " Chart Selection | ASP.NET Core Blazor "

component: "Chart"

description: "Strip Lines are vertical or horizontal lines used to highlight/mark a certain region on the plot area."
---

<!-- markdownlint-disable MD036 -->

# Selection

Chart provides selection support for the series and its data points on mouse click.

>When Mouse is clicked on the data points, the corresponding series legend will also be selected.

We have different type of selection mode for selecting the data. They are,

* None
* Point
* Series
* Cluster
* DragXY
* DragX
* DragY

## Point

 You can select a point, by setting [`SelectionMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~SelectionMode.html) to point.

{% aspTab template="chart/user-interaction/selection/point-selection", sourceFiles="point-selection.razor" %}

{% endaspTab %}

![Point](images/selection/point-selection-razor.png)

## Series

 You can select a series, by setting [`SelectionMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~SelectionMode.html) to series.

{% aspTab template="chart/user-interaction/selection/series-selection", sourceFiles="series-selection.razor" %}

{% endaspTab %}

![Series](images/selection/series-selection-razor.png)

## Cluster

You can select the points that corresponds to the same index in all the series, by setting [`SelectionMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~SelectionMode.html) to cluster.

{% aspTab template="chart/user-interaction/selection/cluster-selection", sourceFiles="cluster-selection.razor" %}

{% endaspTab %}

![Series](images/selection/cluster-selection-razor.png)

## Rectangular selection

**DragXY, DragX and DragY**

To fetch the collection of data under a particular region, you have to set [`SelectionMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~SelectionMode.html) as `DragXY`.

* DragXY - Allows us to select data with respect to horizontal and vertical axis.
* DragX - Allows us to select data with respect to horizontal axis.
* DragY - Allows us to select data with respect to vertical axis.

The selected data’s are returned as an array collection in the `DragComplete` event.

{% aspTab template="chart/user-interaction/selection/drag", sourceFiles="drag.razor" %}

{% endaspTab %}

![Rectangular selection](images/selection/drag-razor.png)

## Selection type

You can select multiple points or series, by enabling the [`IsMultiSelect`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~IsMultiSelect.html) property.

{% aspTab template="chart/user-interaction/selection/selection-type", sourceFiles="selection-type.razor" %}

{% endaspTab %}

## Selection on load

You can able to select a point or series programmatically on a chart using
[`SelectedDataIndexes`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~SelectedDataIndexes.html)
property.

{% aspTab template="chart/user-interaction/selection/onload", sourceFiles="onload.razor" %}

{% endaspTab %}

## Legend Selection

You can able to select a point or series through on legend using
[`ToggleVisibility`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartLegendSettings~_toggleVisibility.html) property.

{% aspTab template="chart/user-interaction/selection/selection-legend", sourceFiles="selection-legend.razor" %}

{% endaspTab %}

## Customization for selection

You can apply custom style to selected points or series with [`SelectionStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~SelectionStyle.html)
property.

{% aspTab template="chart/user-interaction/selection/custom-selection", sourceFiles="custom-selection.razor" %}

{% endaspTab %}

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)