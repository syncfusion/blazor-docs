<!-- markdownlint-disable MD036 -->

# Data Editing

## Enable Data Editing

It provides drag and drop support to the rendered points. Now, we can change the location or value of the point based on its `y` value.  To enable the data editing, set the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartDragSettings.html#Syncfusion_Blazor_Charts_ChartDragSettings_Enable) property to true in the `ChartDataEditSettings` of the series. Also, we can set color using [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartDragSettings.html#Syncfusion_Blazor_Charts_ChartDragSettings_Fill) property and set the data editing minimum and maximum range using [`MinY`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartDragSettings.html#Syncfusion_Blazor_Charts_ChartDragSettings_MinY) and [`MaxY`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartDragSettings.html#Syncfusion_Blazor_Charts_ChartDragSettings_MaxY) properties.

{% aspTab template="chart/user-interaction/data-editing/enable", sourceFiles="data-editing.razor" %}

{% endaspTab %}

![ Enable Data Editing](images/data-editing/data-editing-razor.png)

## See Also

* [Tooltip](./tool-tip)
* [Legend](./legend)
* [Marker](./data-markers)