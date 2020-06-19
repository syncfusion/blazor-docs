---
title: " Chart Appearance | ASP.NET Core Blazor "

component: "Chart"

description: "We can customize chart appearance by using color palette, point level customization, chart area cutomization, title and margin customizations."
---

# Appearance

## Custom Color Palette

You can customize the default color of series or points by providing a custom color palette of your choice by
using the [`Palettes`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~Palettes.html) property.

{% aspTab template="chart/series/column/custom", sourceFiles="custom.razor" %}

{% endaspTab %}

![Custom Color Palette](images/appearance/custom-razor.png)

<!-- markdownlint-disable MD036 -->

## Chart Area Customization

<!-- markdownlint-disable MD036 -->

**Customize the Chart Background**

<!-- markdownlint-disable MD013 -->
Using [`Background`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~Background.html) and [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~Border.html) properties, you can change the background color and border of the chart.

{% aspTab template="chart/series/column/area", sourceFiles="area.razor" %}

{% endaspTab %}

![Customize the Chart Background](images/appearance/area-razor.png)

**Chart Margin**

You can set margin for chart from its container through [`Margin`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~Margin.html) property.

{% aspTab template="chart/series/column/margin", sourceFiles="margin.razor" %}

{% endaspTab %}

**Chart Area Background**

The chart area background can be customized by using the [`Background`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartAreaModel~Background.html)
property in the [`ChartArea`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~ChartArea.html).

{% aspTab template="chart/series/column/background", sourceFiles="background.razor" %}

{% endaspTab %}

## Animation

You can customize animation for a particular series using [`Animation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Animation.html) property. You can enable or disable animation of the series using [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AnimationModel~Enable.html) property. [`Duration`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AnimationModel~Duration.html) specifies the duration of an animation and [`Delay`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AnimationModel~Duration.html) allows us to start the animation at desire time.

{% aspTab template="chart/series/column/animation", sourceFiles="animation.razor" %}

{% endaspTab %}

## Chart Title

Chart can be given a title using [`Title`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~Title.html) property, to show the information about the data plotted.

{% aspTab template="chart/series/column/title", sourceFiles="title.razor" %}

{% endaspTab %}

![Chart Title](images/appearance/title-razor.png)

## Chart SubTitle

Chart can be given a subtitle using [`SubTitle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~SubTitle.html) property, to show the information about the data plotted.

{% aspTab template="chart/series/column/subtitle", sourceFiles="subtitle.razor" %}

{% endaspTab %}

![Chart SubTitle](images/appearance/subtitle-razor.png)

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)