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

 You can select a point, by setting [`SelectionMode`](https://help.syncfusion.com/cr/blazor/) to point.

{% aspTab template="chart/user-interaction/selection/point-selection", sourceFiles="point-selection.razor" %}

{% endaspTab %}

![Point](images/selection/point-selection-razor.png)

## Series

 You can select a series, by setting [`SelectionMode`](https://help.syncfusion.com/cr/blazor/) to series.

{% aspTab template="chart/user-interaction/selection/series-selection", sourceFiles="series-selection.razor" %}

{% endaspTab %}

![Series](images/selection/series-selection-razor.png)

## Cluster

You can select the points that corresponds to the same index in all the series, by setting [`SelectionMode`](https://help.syncfusion.com/cr/blazor/) to cluster.

{% aspTab template="chart/user-interaction/selection/cluster-selection", sourceFiles="cluster-selection.razor" %}

{% endaspTab %}

![Series](images/selection/cluster-selection-razor.png)

## Rectangular selection

**DragXY, DragX and DragY**

To fetch the collection of data under a particular region, you have to set [`SelectionMode`](https://help.syncfusion.com/cr/blazor/) as `DragXY`.

* DragXY - Allows us to select data with respect to horizontal and vertical axis.
* DragX - Allows us to select data with respect to horizontal axis.
* DragY - Allows us to select data with respect to vertical axis.

The selected data’s are returned as an array collection in the `DragComplete` event.

{% aspTab template="chart/user-interaction/selection/drag", sourceFiles="drag.razor" %}

{% endaspTab %}

![Rectangular selection](images/selection/drag-razor.png)

## Selection type

You can select multiple points or series, by enabling the [`IsMultiSelect`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.TabItem.html#Syncfusion_Blazor_Navigations_TabItem_Content) property.

{% aspTab template="chart/user-interaction/selection/selection-type", sourceFiles="selection-type.razor" %}

{% endaspTab %}

## Selection on load

You can able to select a point or series programmatically on a chart using
[`SelectedDataIndexes`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotCellSelectedEventArgs.html#Syncfusion_Blazor_PivotView_PivotCellSelectedEventArgs_SelectedCellsInfo)
property.

{% aspTab template="chart/user-interaction/selection/onload", sourceFiles="onload.razor" %}

{% endaspTab %}

## Legend Selection

You can able to select a point or series through on legend using
[`ToggleVisibility`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartLegendSettings.html) property.

{% aspTab template="chart/user-interaction/selection/selection-legend", sourceFiles="selection-legend.razor" %}

{% endaspTab %}

## Customization for selection

You can apply custom style to selected points or series with [`SelectionStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_SelectionStyle)
property.

{% aspTab template="chart/user-interaction/selection/custom-selection", sourceFiles="custom-selection.razor" %}

{% endaspTab %}

**Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)