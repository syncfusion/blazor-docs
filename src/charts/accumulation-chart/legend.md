---
title: "Accumulation Chart Legend | ASP.NET Core Blazor "

component: "Accumulation Chart"

description: "Accumulation chart legend is used to give additional information about the chart series."
---

# Legend

As like a chart, the legend is also available for accumulation charts, which gives information about the points. By default, the legend will be placed on the right, if the width of the chart is high or will be placed on the bottom, if the height of the chart is high. Here, the legend for a point can be collapsed by giving the empty string to the x value of the point.

{% aspTab template="chart/accumulation-charts/legend/default", sourceFiles="default.razor" %}

{% endaspTab %}

![Legend](images/legend/default-razor.png)

## Position and Alignment

By using the [`Position`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartLegendSettings~Position.html) property, you can position the legend at the `Left`, `Right`, `Top` or `Bottom` of the chart.
You can also align the legend to `Center`, `Far` or `Near` to the chart using the [`Alignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartLegendSettings~Alignment.html) property.

{% aspTab template="chart/accumulation-charts/legend/position", sourceFiles="position.razor" %}

{% endaspTab %}

![Position and Alignment](images/legend/position-razor.png)

## Legend Shape

To change the legend icon, use the [`LegendShape`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~LegendShape.html) property in the `Series`. By default, legend icon is `SeriesType`.

{% aspTab template="chart/accumulation-charts/legend/legend-shape", sourceFiles="legend-shape.razor" %}

{% endaspTab %}

![Legend Shape](images/legend/legend-shape-razor.png)

## Legend Size

The legend size can be changed by using the [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartLegendSettings~Width.html) and [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartLegendSettings~Height.html) properties of the `LegendSettings`.

{% aspTab template="chart/accumulation-charts/legend/size", sourceFiles="size.razor" %}

{% endaspTab %}

![Legend Size](images/legend/size-razor.png)

## Legend Item Size

You can customize the size of the legend items by using the [`ShapeHeight`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartLegendSettings~ShapeHeight.html) and [`ShapeWidth`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartLegendSettings~ShapeWidth.html) properties.

{% aspTab template="chart/accumulation-charts/legend/item-size", sourceFiles="item-size.razor" %}

{% endaspTab %}

![Legend Item Size](images/legend/item-size-razor.png)

## Paging for Legend

Paging will be enabled by default, when the legend items exceeds the legend bounds. You can view the each legend item by navigating through the pages.

{% aspTab template="chart/accumulation-charts/legend/paging", sourceFiles="paging.razor" %}

{% endaspTab %}

![Paging for Legend](images/legend/paging-razor.png)

* [Grouping](./grouping/)
* [Datalabel](./data-label/)