---
title: " Chart Appearance | ASP.NET Core Blazor "

component: "Chart"

description: "We can set chart size manually by using width and height properties. We can set percentage or pixel size values to the chart."
---

# Chart Dimensions

## Size for Container

Chart can render to its container size. You can set the size inline or through CSS as demonstrated below.

{% aspTab template="chart/getting-started/size", sourceFiles="size.razor" %}

{% endaspTab %}

## Size for Chart

You can also set size for chart directly through [`Width`](https://help.syncfusion.com/cr/cref_files/aspnetmvc-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.Chart~Width.html) and
[`Height`](https://help.syncfusion.com/cr/cref_files/aspnetmvc-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.Chart~Height.html) properties.

<!-- markdownlint-disable MD036 -->
**In Pixel**
<!-- markdownlint-disable MD036 -->

You can set the size of chart in pixel as demonstrated below.

{% aspTab template="chart/getting-started/pixel", sourceFiles="pixel.razor" %}

{% endaspTab %}

![Size for Chart](images/chart-dimensions/pixel.png)

**In Percentage**

By setting value in percentage, chart gets its dimension with respect to its container. For example,
when the height is ‘50%’, chart renders to half of the container height.

{% aspTab template="chart/getting-started/percentage", sourceFiles="percentage.razor" %}

{% endaspTab %}

> Note:  When you do not specify the size, it takes `450px` as the height and window size as its width.

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)