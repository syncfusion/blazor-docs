---
title: "Funnel | ASP.NET Core Blazor "

component: "Accumulation Chart"

description: "The funnel chart displays series value as progressively decreasing amount to hundred percent in total"
---

# Funnel Chart

To render a funnel series, use the series [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Type.html)
as `Funnel`.

{% aspTab template="chart/accumulation-charts/funnel/default", sourceFiles="default.razor" %}

{% endaspTab %}

![Funnel Chart](../images/funnel/default-razor.png)

## Size

The size of the funnel chart can be customized by using the  [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Width.html) and [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Height.html) properties.

{% aspTab template="chart/accumulation-charts/funnel/size", sourceFiles="size.razor" %}

{% endaspTab %}

![Size](../images/funnel/size-razor.png)

## Neck Size

The neck size can be customized by using the [`NeckWidth`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~NeckWidth.html) and [`NeckHeight`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~NeckHeight.html) properties.

{% aspTab template="chart/accumulation-charts/funnel/neck-size", sourceFiles="neck-size.razor" %}

{% endaspTab %}

![Neck Size](../images/funnel/neck-size-razor.png)

## Gap Between the Segments

Funnel chart provides options to customize the space between the segments by using the [`GapRatio`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~GapRatio.html) property of the
series. It takes values from 0 to 1.

{% aspTab template="chart/accumulation-charts/funnel/gap", sourceFiles="gap.razor" %}

{% endaspTab %}

![Gap Between the Segments](../images/funnel/gap-razor.png)

## Explode

Points can be exploded on mouse click by setting the [`Explode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Explode.html) property to true. You can also explode the point
on load using [`ExplodeIndex`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~ExplodeIndex.html). Explode distance can be set by using [`ExplodeOffset`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~ExplodeOffset.html) property.

{% aspTab template="chart/accumulation-charts/funnel/explode", sourceFiles="explode.razor" %}

{% endaspTab %}

![Explode](../images/funnel/explode-razor.png)

## Smart Data Label

Arrange the data label smartly on left side of the funnel and pyramid chart, when they overlaps with each other.

{% aspTab template="chart/accumulation-charts/funnel/smart-data-label", sourceFiles="smart-data-label.razor" %}

{% endaspTab %}

![Smart Data Label](../images/funnel/smart-data-label-razor.png)

## See Also

* [Data label](../data-label/)
* [Grouping](../grouping/)
