---
title: " Chart Legend | ASP.NET Core Blazor "

component: "Chart"

description: "Chart legend provides information about the series rendered in the chart.It has different alignment, shapes and customization properties. "
---

# Legend

Legend provides information about the series rendered in the chart.

## Enable Legend

You can use legend for the chart by setting the [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartLegendSettings~Visible.html)
property to true in [`LegendSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~LegendSettings.html) object.

{% aspTab template="chart/getting-started/legend", sourceFiles="legend.razor" %}

{% endaspTab %}

![Enable Legend](images/legend/legend-razor.png)

## Position and Alignment

By using the [`Position`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartLegendSettings~Position.html) property, you can position the legend
at left, right, top or bottom of the chart. The legend is positioned at the bottom of the chart, by default.

{% aspTab template="chart/axis/legend/default", sourceFiles="default.razor" %}

{% endaspTab %}

Custom position helps you to position the legend anywhere in the chart using x, y coordinates.

{% aspTab template="chart/axis/legend/position", sourceFiles="position.razor" %}

{% endaspTab %}

<!-- markdownlint-disable MD036 -->

**Legend Alignment**

<!-- markdownlint-disable MD036 -->

You can align the legend as `Center`, `Far` or `Near` to the chart using
[`Alignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartLegendSettings~Alignment.html) property.

{% aspTab template="chart/axis/legend/alignment", sourceFiles="alignment.razor" %}

{% endaspTab %}

![Legend Alignment](images/legend/alignment-razor.png)

## Customization

To change the legend icon shape, you can use [`LegendShape`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~LegendShape.html) property in the Series. By default legend icon shape is `SeriesType`.

{% aspTab template="chart/axis/legend/custom", sourceFiles="custom.razor" %}

{% endaspTab %}

**Legend Size**

By default, legend takes 20% - 25% of the chart's height, when it is placed on top or bottom position and 20% - 25% of the
chart's width, when placed on left or right position of the chart. You can change this default legend size by using the
[`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartLegendSettings~Width.html) and [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartLegendSettings~Height.html) property of the `LegendSettings`.

{% aspTab template="chart/axis/legend/size", sourceFiles="size.razor" %}

{% endaspTab %}

**Legend Item Size**

You can customize the size of the legend items by using the [`ShapeHeight`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartLegendSettings~ShapeHeight.html)
and [`ShapeWidth`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartLegendSettings~ShapeWidth.html) property.

{% aspTab template="chart/axis/legend/item-size", sourceFiles="item-size.razor" %}

{% endaspTab %}

![Legend Alignment](images/legend/item-size-razor.png)

**Paging for Legend**

Paging will be enabled by default, when the legend items exceeds the legend bounds. You can view each legend items by navigating between the pages using navigation buttons.

{% aspTab template="chart/axis/legend/paging", sourceFiles="paging.razor" %}

{% endaspTab %}

## Series Selection on Legend

By default, legend click enables you to collapse the series visibility. On other hand, if you need to select a series through legend click, disable the
[`ToggleVisibility`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartLegendSettings~ToggleVisibility.html).

{% aspTab template="chart/axis/legend/selection", sourceFiles="selection.razor" %}

{% endaspTab %}

## Collapsing Legend Item

By default, series name will be displayed as legend. To skip the legend for a particular series, you can give empty string to the series name.

{% aspTab template="chart/axis/legend/collapse", sourceFiles="collapse.razor" %}

{% endaspTab %}

![Collapsing Legend Item](images/legend/collapse-razor.png)

## See Also

* [Data label](./data-labels)
* [Marker](./data-markers)