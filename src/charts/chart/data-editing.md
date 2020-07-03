---
title: "Chart Data Editing | ASP.NET Core Blazor"
component: "Chart"
description: "Data editing is one of the user interaction feature. It provides the chart data that to change their value by using mouse cursor"
---

<!-- markdownlint-disable MD036 -->

# Data Editing

## Enable Data Editing

It provides drag and drop support to the rendered points. Now, we can change the location or value of the point based on its `y` value.  To enable the data editing, set the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartDragSettings~Enable.html) property to true in the drag settings of the series. Also, we can set color using [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartDragSettings~Fill.html) property and set the data editing minimum and maximum range using [`MinY`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartDragSettings~MinY.html) and [`MaxY`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartDragSettings~MaxY.html) properties.

{% aspTab template="chart/user-interaction/data-editing/enable", sourceFiles="data-editing.razor" %}

{% endaspTab %}

![ Enable Data Editing](images/data-editing/data-editing-razor.png)

## See Also

* [Tooltip](./tool-tip)
* [Legend](./legend)
* [Marker](./data-markers)