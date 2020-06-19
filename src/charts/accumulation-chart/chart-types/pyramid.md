---
title: "Pyramid | ASP.NET Core Blazor "

component: "Accumulation Chart"

description: "The pyramid chart displays series value as progressively decreasing amount to hundred percent in total"
---

# Pyramid Chart

To render a pyramid series, use the series [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Type.html)
as `Pyramid`.

{% aspTab template="chart/accumulation-charts/pyramid/default", sourceFiles="default.razor" %}

{% endaspTab %}

![Pyramid Chart](../images/pyramid/default-razor.png)

## Mode

The Pyramid chart supports linear and surface modes of rendering. The default type of the
[`PyramidMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~PyramidMode.html) is `Linear`.

{% aspTab template="chart/accumulation-charts/pyramid/mode", sourceFiles="mode.razor" %}

{% endaspTab %}

![Mode](../images/pyramid/mode-razor.png)

## Size

The size of the pyramid chart can be customized by using the  [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Width.html) and [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Height.html) properties.

{% aspTab template="chart/accumulation-charts/pyramid/size", sourceFiles="size.razor" %}

{% endaspTab %}

![Size](../images/pyramid/size-razor.png)

## Gap Between the Segments

Pyramid chart provides options to customize the space between the segments by using the [`GapRatio`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~GapRatio.html) property of the
series. It takes values from 0 to 1.

{% aspTab template="chart/accumulation-charts/pyramid/gap", sourceFiles="gap.razor" %}

{% endaspTab %}

![Gap Between the Segments](../images/pyramid/gap-razor.png)

## Explode

Points can be exploded on mouse click by setting the [`Explode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Explode.html) property to true. You can also explode the point
on load using [`ExplodeIndex`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~ExplodeIndex.html). Explode distance can be set by using [`ExplodeOffset`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~ExplodeOffset.html) property.

{% aspTab template="chart/accumulation-charts/pyramid/explode", sourceFiles="explode.razor" %}

{% endaspTab %}

![Explode](../images/pyramid/explode-razor.png)

## See Also

* [Data label](../data-label/)
* [Grouping](../grouping/)