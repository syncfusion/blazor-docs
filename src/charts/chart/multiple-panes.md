---
title: " Chart Multiple-panes | ASP.NET Core Blazor "

component: "Chart"

description: "Chart can be divided multiple rows and columns. Axes are rendering based on row index or column index in pane."
---

# Multiple Panes

Chart area can be divided into multiple panes using [`Rows`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.GridEvents-1.html#Syncfusion_Blazor_Grids_GridEvents_1_OnActionBegin) and
[`Columns`](https://help.syncfusion.com/cr/blazor/).

## Rows

To split the chart area vertically into number of rows, use `Rows` property of the chart.

* You can allocate space for each row by using the [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartRow.html#Syncfusion_Blazor_Charts_ChartRow_Height)
property. The value can be either in percentage or in pixel.
* To associate a vertical axis to a particular row, specify its index to
[`RowIndex`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartAxis.html#Syncfusion_Blazor_Charts_ChartAxis_RowIndex) property of the axis.
* To customize each row’s bottom line, use [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartRow.html#Syncfusion_Blazor_Charts_ChartRow_Border) property.

{% aspTab template="chart/axis/multiple-panes/row", sourceFiles="row.razor" %}

{% endaspTab %}

![Rows](images/multiple-panes/row.png)

For spanning the vertical axis along multiple row, you can use [`Span`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartAxis.html#Syncfusion_Blazor_Charts_ChartAxis_Span) property of an axis.

{% aspTab template="chart/axis/multiple-panes/row-span", sourceFiles="row-span.razor" %}

{% endaspTab %}

![Rows](images/multiple-panes/row-span.png)

## Columns

To split the chart area horizontally into number of columns, use [`Columns`](https://help.syncfusion.com/cr/blazor/) property of the chart.

* You can allocate space for each column by using the [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartColumn.html#Syncfusion_Blazor_Charts_ChartColumn_Width)
property. The given width can be either in percentage or in pixel.
* To associate a horizontal axis to a particular column, specify its index to
[`ColumnIndex`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartAxis.html#Syncfusion_Blazor_Charts_ChartAxis_ColumnIndex) property of the axis.
* To customize each column’s bottom line, use [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartColumn.html#Syncfusion_Blazor_Charts_ChartColumn_Border) property.

{% aspTab template="chart/axis/multiple-panes/column", sourceFiles="column.razor" %}

{% endaspTab %}

![Columns](images/multiple-panes/Column.png)

For spanning the horizontal axis along multiple column, you can use [`Span`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartAxis.html#Syncfusion_Blazor_Charts_ChartAxis_Span) property of an axis.

{% aspTab template="chart/axis/multiple-panes/column-span", sourceFiles="column-span.razor" %}

{% endaspTab %}

![Columns](images/multiple-panes/Column-span.png)

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)